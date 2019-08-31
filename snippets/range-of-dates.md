## How to easily generate a range of dates in Python

Pandas library has a [`date_range`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.date_range.html) function!

```
$ pip install pandas
```

```
import pandas as pd
date_list = pd.date_range(pd.datetime.today(), periods=100).tolist()
```

These are [pandas Timestamp](https://pandas.pydata.org/pandas-docs/version/0.23.4/generated/pandas.Timestamp.html) objects

To get string dates out of these, use each `Timestamp` obejct's `strftime` method, which mimicks the formatting of Python's [strftime](https://docs.python.org/3/library/datetime.html#strftime-strptime-behavior):
```
print(my_timestamp.strftime("%Y-%m-%d")
>>> 12/06/2019
```
