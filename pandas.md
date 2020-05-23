df.describe()   # show basic statistics
df.info()   # show data type, count, null or not
df.isnull().sum()  # show number of null in each column
df = df.sort_values('Date')  # sort based on Date column
df.rename(columns={'Data':'ds', 'Price':'y'}) # rename column
df.index # get the index column
df.describe(include='all')
new_index = pd.date_range("2016-01-01", periods=len(s), freq="D")
