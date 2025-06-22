# Reading a CSV file
There are different ways to read and write CSV file in python. Datatable being the best in terms of performance. 

## Reading CSV file
```python
import pandas as pd
import datatable as dt
from dask import dataframe as dd

file = 'df.csv'

#read uing pandas read_csv()
df = pd.read_csv(file)

#read using datatable
dt_df = dt.fread(file)
dt_df = dt.to_pandas()

#read using Dask
dd_df = dd.read_csv(file)
dd_df = dd_df.compute()
```

## Writing to CSV file
```python
file = 'df.csv'

#pandas dataframe
df.to_csv(file)

#Datatable
dt_df = dt.Frame(df)
dt_df.to_csv(file)

#Dask
dsk_df = dd.from_pandas(df, npartitions=1)
dsk_df.to_csv(file)
```
