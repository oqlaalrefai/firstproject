# pandas

- import the package
`import pandas as pd`

- Object creation
  - series : Creating a Series by passing a list of values
`s = pd.Series([1, 3, 5, np.nan, 6, 8])`
  - Creating a DataFrame by passing a NumPy array, with a datetime index and labeled columns
`dates = pd.date_range("20130101", periods=6)`
    - Creating a DataFrame by passing a dict of objects that can be converted to series-like.

### Viewing data
- to view the top and bottom rows of the frame:
  - `df.head()`
  - `df.tail()`
- Display the index, columns:
  - df.index
  - df.columns
** NumPy arrays have one dtype for the entire array, while pandas DataFrames have one dtype per column **
- DataFrame.to_numpy() does not include the index or column labels in the output.
- Transposing your data:`df.T`
- Sorting by an axis:`df.sort_index(axis=1, ascending=False)`
- sorting by value :`df.sort_values(by="B")`

### Getting

- Selecting a single column, which yields a Series, equivalent to `df.A`
- Selecting via [], which slices the rows.`df[0:3]`

### Selection by label

- For getting a cross section using a label:`df.loc[dates[0]]`
- Selecting on a multi-axis by label: `df.loc[:, ["A", "B"]]`
- Showing label slicing, both endpoints are included: `df.loc["20130102":"20130104", ["A", "B"]]`
- Reduction in the dimensions of the returned object: `df.loc["20130102", ["A", "B"]]`
- For getting a scalar value: `df.loc[dates[0], "A"]`
- For getting fast access to a scalar (equivalent to the prior method):`df.at[dates[0], "A"]`

### Selection by position

- Select via the position of the passed integers: `df.iloc[3]`
- By integer slices, acting similar to NumPy/Python: `df.iloc[3:5, 0:2]`
- By lists of integer position locations, similar to the NumPy/Python style: `df.iloc[[1, 2, 4], [0, 2]]`
- For slicing rows explicitly: `df.iloc[1:3, :]`
- For slicing columns explicitly: `df.iloc[:, 1:3]`
- For getting a value explicitly: `df.iloc[1, 1]`
- For getting fast access to a scalar (equivalent to the prior method): `df.iat[1, 1]`

### Boolean indexing

Using a single column’s values to select data.

### Setting

Setting a new column automatically aligns the data by the indexes.

### Missing data

pandas primarily uses the value `np.nan` to represent missing data. It is by default not included in computations. See the Missing Data section.
Reindexing allows you to change/add/delete the index on a specified axis. This returns a copy of the data.

### Operations

- Stats
Operations in general exclude missing data.Performing a descriptive statistic:`mean`
- Apply
Applying functions to the data: `df.apply(np.cumsum)`
- Histogramming
- String Methods
Series is equipped with a set of string processing methods in the str attribute that make it easy to operate on each element of the array, as in the code snippet below. Note that pattern-matching in str generally uses regular expressions by default (and in some cases always uses them).
### Merge

- Concat
pandas provides various facilities for easily combining together Series and DataFrame objects with various kinds of set logic for the indexes and relational algebra functionality in the case of join / merge-type operations
- Join
SQL style merges
- Grouping :By “group by” we are referring to a process involving one or more of the following steps:

  - Splitting the data into groups based on some criteria
  - Applying a function to each group independently
  - Combining the results into a data structure
### Reshaping
- Stack : The stack() method “compresses” a level in the DataFrame’s columns.
- Pivot tables 
- Time series : pandas has simple, powerful, and efficient functionality for performing resampling operations during frequency conversion (e.g., converting secondly data into 5-minutely data)
- Categoricals : pandas can include categorical data in a DataFrame. For full docs, see the categorical introduction and the API documentation.

### Plotting
- The `close()` method is used to close a figure window.
- the `plot()` method is a convenience to plot all of the columns with labels


### Getting data in/out
- CSV
  - Writing to a csv file. `df.to_csv("foo.csv")`
  - Reading from a csv file.`pd.read_csv("foo.csv")`
- HDF5
  - Writing to a HDF5 Store. `df.to_hdf("foo.h5", "df")`
  - Reading from a HDF5 Store. `pd.read_hdf("foo.h5", "df")`
- Excel
- Writing to an excel file `df.to_excel("foo.xlsx", sheet_name="Sheet1")`
- Reading from an excel file. `pd.read_excel("foo.xlsx", "Sheet1", index_col=None, na_values=["NA"])`

### Gotchas
If you are attempting to perform an operation you might see an exception like:
``` ValueError: The truth value of an array is ambiguous. Use a.empty, a.any() or a.all(). ```


