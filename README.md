# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
NAME : VARSHINI S
REG NO : 212222220056
```
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/22d4b4d9-9074-47c2-8f78-6c337b83d158)

```
df.info()
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/e104190a-45cb-4220-a9e4-e5cb1290271b)

```
df.set_index("PassengerId",inplace = True)
df.describe()
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/01c07561-84b7-4b49-9dd0-5a57f94020c3)

```
df.shape
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/2f6e2315-f94d-4e4c-9bab-aab8eb76639a)

```
df.nunique()
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/9ba7083f-7f66-429d-9458-1d9cec084c87)

```
### CATEGORICAL DATA ANALYSIS
```
df["Survived"].value_counts()
per = (df['Survived'].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/Yamunaasri/EXNO2DS/assets/115707860/07f72523-9dc5-47c0-bd62-4b3e4510b0f9)
```
### UNIVARIATE ANALYSIS
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/varshxnx/EXNO2DS/assets/122253525/9bb746ec-dda8-4883-8793-ed8a573d8e75)

```
### BIVARIATE ANALYSIS
```
fig, ax1 = plt.subplots(figsize=(5,5))
graph=sns.countplot(ax=ax1,x= 'Survived', data=df)
graph.set_xticklabels (graph.get_xticklabels (), rotation=90)
for p in graph.patches:
  height = p.get_height()
  graph.text(p.get_x()+p.get_width()/2., height + 0.1, height,ha="center")
```
![image](https://github.com/Yamunaasri/EXNO2DS/assets/115707860/c0d268af-de9d-45aa-9d1b-ef12127d8425)
```

# RESULT
Thus, the outputs verifies that the data set has been applied the EDA process and methods,
