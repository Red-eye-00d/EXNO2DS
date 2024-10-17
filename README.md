# EXNO2DS
SUDHARSANAN U
24900788
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
        import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
image

df.info
image

df.shape
(891,120
df.nunique()
image

df['Survived'].value_counts()
image

sns.countplot(data=df,x="Survived",hue="Survived")
image

df
image

df.Pclass.unique()
array([3,1,2])
df.rename(columns={'Sex':'Gender'},inplace=True)
df
image

sns.catplot(x="Gender",col='Survived',hue="Gender",kind="count",data=df,height=5,aspect=.7)
image

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
image

df.boxplot(column="Age",by="Survived")
image

sns.scatterplot(x=df["Age"],y=df["Fare"])
image

sns.jointplot(x="Age",y="Fare",data=df)
image

fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
image

sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
image

ndf = df.select_dtypes(include='number')
corr=ndf.corr()
sns.heatmap(corr,annot=True)
Uploading image.png…

image

sns.pairplot(df)
image

# RESULT
        Thus the output verifies that the given data set has been applied the EDA process and methods.
