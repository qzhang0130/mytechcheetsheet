import seaborn as sns
sns.catplot(x="release_date_weekday", y="revenue", data=train)
sns.distplot(train["runtime"], bins=40, kde=False)
sns.scatterplot(train["runtime"], train["revenue"])
sns.pairplot(df_train)
