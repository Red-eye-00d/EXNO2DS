# EXNO2DS
##  SUDHARSANAN U
## 24900788
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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/04084b84-3011-47a9-b879-d576d5d0881b)
```
df.info
```
![image](https://github.com/user-attachments/assets/e8943f04-b630-4b31-8ec0-af6ded26fcf3)
```
df.shape
```
```
(891,120
```
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/fe652ce2-b3c8-4bb6-a15e-03714170b2c3)
```
df['Survived'].value_counts()
```
![image](https://github.com/user-attachments/assets/0c7c5545-6f7c-4f24-b388-8d0673394853)

```
sns.countplot(data=df,x="Survived",hue="Survived")
```
![image](https://github.com/user-attachments/assets/986a580a-0f6f-4b3b-96a1-72a8835984ed)

```
df
```
![image](https://github.com/user-attachments/assets/e4389549-de49-479b-9434-d4464b70d6a6)
```
df.Pclass.unique()
```
```
array([3,1,2])
```
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/8306e4c1-b9a7-4745-8561-cf35d4083568)

```
sns.catplot(x="Gender",col='Survived',hue="Gender",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/1c23e59c-6334-4af8-9b5e-8e8e9430fb44)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/c1b79060-70fd-40f0-9a12-8581dfafccf8)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/ddf82923-0360-4dfa-b20f-89d853f1769c)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/9083b01d-4320-47e5-b008-ea18fbd3cddb)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/7016386a-1d4e-4813-8282-c72505d8031a)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/2584c36a-eda3-49ad-9a75-d57c126cb08c)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/9c817d99-a843-4a80-8220-4af6516ab440)

```
ndf = df.select_dtypes(include='number')
corr=ndf.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/c9900242-80a4-44e7-892f-9b6f1a9c4e1d)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/9be7d735-725c-402c-9b09-89806eff921c)




# RESULT
Thus the output verifies that the given data set has been applied the EDA process and methods.
