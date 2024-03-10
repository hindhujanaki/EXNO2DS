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
 import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
 dt=pd.read_csv("/content/titanic_dataset.csv")
 dt
![alt text](<Screenshot 2024-03-09 054754.png>) 
 dt.head()
 ![alt text](<Screenshot 2024-03-09 054818.png>)
 dt.tail()
![alt text](<Screenshot 2024-03-09 054832.png>) 
 dt.info()
![alt text](<Screenshot 2024-03-09 054845.png>) 
 dt.shape()
![alt text](<Screenshot 2024-03-09 054908.png>) 
 dt.set_index("PassengerID",inplace=True)
dt.describe()

 ![alt text](<Screenshot 2024-03-09 054941.png>)
 dtnunique()
 ![alt text](<Screenshot 2024-03-09 054949.png>) 
 dt["Survived"].value_counts()
![alt text](<Screenshot 2024-03-09 054958.png>) 
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
![alt text](<Screenshot 2024-03-09 055011.png>)
sns.countplot(data=dt,x="Survived")
![alt text](<Screenshot 2024-03-09 055028.png>)
dt
![alt text](<Screenshot 2024-03-09 055043.png>)
dt.Pclass.unique()
![alt text](<Screenshot 2024-03-09 055054.png>)
dt.rename(columns = {'Sex':'Gender'},inplace=True)

dt
![alt text](<Screenshot 2024-03-09 055115.png>)
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
![alt text](<Screenshot 2024-03-09 055136.png>)
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
![alt text](<Screenshot 2024-03-09 055156.png>)
dt.boxplot(column="Age",by="Survived")
![alt text](<Screenshot 2024-03-09 055207.png>)
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
![alt text](<Screenshot 2024-03-09 055217.png>)
sns.jointplot(x="Age",y="Fare",data=dt)
![alt text](<Screenshot 2024-03-09 055308.png>)

fig, ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
![alt text](<Screenshot 2024-03-09 055244.png>)
sns.catplot(data=dt,col="Survived",!x="Gender",hue="Pclass",kind="count")
![alt text](<Screenshot 2024-03-09 055322.png>)
corr=dt.corr()
sns.heatmap(corr,annot=True)
![alt text](<Screenshot 2024-03-10 082054.png>)
sns.pairplot(dt)
![alt text](<Screenshot 2024-03-10 082218.png>)


# RESULT
        Thus the program was executed.
