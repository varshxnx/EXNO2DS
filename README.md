# EXNO2DS-Exploratory Data Analysis
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
 The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Developed by: Varshini S
### Register no: 212222220056
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/ae10f144-8714-4c89-bb2b-e72644d6b67a)

```py
df.info()
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/32eb5764-d40e-4860-bf15-f210856c18a7)


```py
df.shape
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/45eb606b-2a0a-4293-99e5-96ba1bcef25f)


```py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/31c3b1d9-b513-4af3-8c47-44a822532d52)


```py
df.shape
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/7700b367-1983-4d0a-b088-ed7e534c343a)


### Categorical data analysis
```py
df.nunique()
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/aa2f56db-7106-4d5a-8130-441f22e06be1)


```py
df["Survived"].value_counts()
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/aee03f3e-8b6a-4b92-b868-11a19c16e81e)

```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/70910a1b-2c8c-4be5-9545-cab82ef85a2f)


```py
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/7d6cc46a-f6a2-439e-9e0a-57a7e9a59115)

```py
df
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/98059d61-a575-4ac6-8d9f-45ed673e5ca4)


```py
df.Pclass.unique()
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/da6a84b7-b281-480f-9405-08572b4682a5)


```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/4832f420-c29e-4e46-93ec-5c3b8beaed6d)


### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/1da4851a-a5b7-4782-9f44-16d6920bffe2)

```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/3a562565-3ec3-4119-87ce-0767a2ae7b1f)


```py
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/5c97c720-2fcf-4a35-9935-1ba1f6a3368e)


```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/a7d4e79e-d65f-4146-ab1d-8bf1f3f158ff)


```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/f7b4d3b4-fba2-4804-b8df-c38f06fb6d77)


### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/3ef0aab4-364a-4dc7-9847-3eb49d3fc285)


```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/68680e0e-462c-41d1-bd9f-cf140f2a2c39)

# Co-relation
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/595a4a4a-3b0a-44d6-9f70-e3f7c4a44c95)


```py
sns.pairplot(df)
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/1013ebed-fb58-4248-8721-19bc64ce294e)


## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
