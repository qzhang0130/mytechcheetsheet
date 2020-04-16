df.describe()   # show basic statistics
df.info()   # show data type, count, null or not
df.isnull().sum()  # show number of null in each column
df = df.sort_values('Date')  # sort based on Date column
df.rename(columns={'Data':'ds', 'Price':'y'}) # rename column
