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

## CODING AND OUTPUT:
```
import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/c92195b0-7911-4752-8824-b82c9307aa93)

```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/3dde1008-eb76-4512-bd16-75bff12bf244)

```
df.info()
```
![image](https://github.com/user-attachments/assets/fe3ffece-8a06-4482-bf4d-e381dbcb134f)

```
df.set_index("PassengerId",inplace=True)
df
```
![image](https://github.com/user-attachments/assets/0bd28877-1cce-439a-be40-3afc713dc726)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/d5bc6fce-e7bb-4599-b7ab-a5417baa7c18)

```
df.dropna(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/512cbf7b-9873-41a5-86b9-acf7f80fd0c7)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/cd95d0c1-d32a-4712-856e-147086264e8f)

```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/1d6df62a-82d3-45c8-96ee-8530f283609b)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/a8cb1951-36a3-478a-a9c0-097a7d87f619)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/f33112b0-aaec-4eb7-8388-ac1cc91e725a)

```
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/8596c05b-26b8-446c-83a9-bcc3c1035ddd)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/6ece8149-aff4-4b0a-bc53-34a0273c4b5d)

```
df.rename(columns = {'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/4d82e5c2-fb42-4c33-8884-f2694c98cd86)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=1.5)
```

![image](https://github.com/user-attachments/assets/ee42f02f-ea7c-483b-bb9e-4e8f4fa30c0e)

```
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/bf63e60e-7eaa-4ca3-a279-08afeb9410c1)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/3efca6aa-4a96-4b43-9af3-dcff42995cdd)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/4deade48-df25-43d7-9ede-e8ba2585239e)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/38d59380-5c96-4a5a-8354-1857712540b8)

```
import seaborn as sns
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/23e4c97d-45ee-44ca-8ccf-409dece8f987)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/d02177ed-f1dd-42a8-8881-f3b15c1565bf)

```
numerical_df = df.select_dtypes(include=['number'])
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/c044ddca-829e-4aa1-a1f2-0f7acf78ff6b)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/296827da-7541-470a-9a1a-7a816830b67d)

# RESULT:
  Thus, The result has been successfully verified!
