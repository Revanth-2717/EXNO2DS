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
### PROGRAMS:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df=pd.read_csv("titanic_dataset.csv")

df
```
### OUTPUT:
<img width="1437" height="462" alt="image" src="https://github.com/user-attachments/assets/e4651029-b3c2-46c2-a375-c4ae73ca5302" />

## INFORMATION ABOUT THE DATASET:
```python
df.info()
```
### OUTPUT:
<img width="515" height="463" alt="image" src="https://github.com/user-attachments/assets/14fb37c7-cb7d-4787-8908-2bd17e280908" />

## DISPLAY NO OF ROWS AND COLUMNS:
```python
df.shape
```
### OUTPUT:
<img width="162" height="53" alt="image" src="https://github.com/user-attachments/assets/e34d0c98-1b89-4ab5-9a84-44faac97ab8b" />

## DROP THE NULL VALUES:
```PYTHON
df.dropna(inplace=True)
df
```
### OUTPUT:
<img width="1452" height="472" alt="image" src="https://github.com/user-attachments/assets/48546e63-ec1c-4e17-9237-ac59f5675b2f" />

## AFTER DROPPPING THE NULL VALUES(GIVE THE NUMBER OF ROWS AND COLUMNS):
```PYTHON
df.shape
```
### OUTPUT:
<img width="149" height="60" alt="image" src="https://github.com/user-attachments/assets/02ea9635-7359-420d-9f05-c18b23267d3c" />

## SET PASSENGER ID AS INDEX COLUMN:
```PYTHON
df.set_index("PassengerId",inplace=True)
df
```
### OUTPUT:
<img width="1395" height="520" alt="image" src="https://github.com/user-attachments/assets/28d96d17-036b-4991-811f-2bcf12ec0093" />

## STASTISTICS OF THE DATASET:
```PYTHON
df.describe()
```
### OUTPUT:
<img width="765" height="336" alt="image" src="https://github.com/user-attachments/assets/946c977b-00c2-42d7-827c-016c1db5e0aa" />

## CATEGORICAL DATA ANALYSIS:
## USE VALUE COUNT FUNCTION AND PERFROM CATEGORICAL ANALYSIS:
```python
df.nunique()
```
### OUTPUT:
<img width="273" height="316" alt="image" src="https://github.com/user-attachments/assets/c816b5e3-0aef-4718-b7ec-ae53d67c13fb" />

## IT'S COUNTS THE NUMBERS OF UNSURVIVED AND SURVIVED:
```PYTHON
df["Survived"].value_counts()
```
### OUTPUT:
<img width="302" height="97" alt="image" src="https://github.com/user-attachments/assets/a18cba4c-bc71-4978-b605-21c240b63e7c" />

## PERCENTAGE OF UNSURVIVED AND SURVIVED:
```PYTHON
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
### OUTPUT:
<img width="315" height="117" alt="image" src="https://github.com/user-attachments/assets/e1f74ee8-d2a1-4b09-a6b6-90bae57d5e06" />

## IT'S COUNTS THE NUMBERS OF MALE AND FEMALE IN SEX COLUMN:
```PYTHON
df['Sex'].value_counts()
```
### OUTPUT:

<img width="297" height="102" alt="image" src="https://github.com/user-attachments/assets/5444274e-d6f5-4fa8-a011-cf2ce5707967" />

## PERCENTAGE OF MALE AND FEMALE:
```PYTHON
per1=(df['Sex'].value_counts()/df.shape[0]*100).round(2)
per1
```
### OUTPUT:

<img width="284" height="117" alt="image" src="https://github.com/user-attachments/assets/43adaeee-119f-43b8-8b94-23aff97f78eb" />

## COUNTS THE Pclass OF (1,2,3):
```PYTHON
df["Pclass"].value_counts()
```
### OUTPUT:

<img width="303" height="129" alt="image" src="https://github.com/user-attachments/assets/ee6064b3-f239-4dd9-9740-6073c6e3f496" />

## PERCENTAGE OF Pclass:
```PYTHON
per2=(df["Pclass"].value_counts()/df.shape[0]*100).round(2)
per2
```
### OUTPUT:
<img width="295" height="139" alt="image" src="https://github.com/user-attachments/assets/012cbbd7-790a-45a5-80d9-694a72ffcdfb" />


## UNIVARIATE ANALYSIS:
## USE COUNTPLOT AND PERFORM UNIVARIATE ANALYSIS FOR THE "SURVIVED" COLUMN IN TITANIC DATASET:
```PYTHON
sns.countplot(data=df,x="Survived")
```
### OUTPUT:

<img width="808" height="620" alt="image" src="https://github.com/user-attachments/assets/d8222ea5-2960-4688-a90a-cb2077d9c771" />

## HISTOGRAM FOR DISTRIBUTION:
```PYTHON
sns.histplot(df['Survived'], kde=True)
```
### OUTPUT:

<img width="793" height="624" alt="image" src="https://github.com/user-attachments/assets/37ae07a5-dc38-4bad-b5b9-154f40829fa3" />

## KDE PLOT FOR SMOOTH DISTRIBUTION:
```PYTHON
sns.kdeplot(df['Survived'], shade=True)
```
### OUTPUT:

<img width="803" height="640" alt="image" src="https://github.com/user-attachments/assets/39f14f88-7304-4f57-baa0-b3c088a3f9db" />

## COUNT PLOT TO SEE THE FREQUENCY OF CATEGORIES:
```PYTHON
sns.countplot(x='Embarked', data=df)
```
### OUTPUT:

<img width="813" height="633" alt="image" src="https://github.com/user-attachments/assets/93c22db6-ceb6-4cf5-bffe-fac7f8aaba03" />

## IDENTIFY UNIQUE VALUES IN "PASSENGER CLASS" COLUMN:
```PYTHON
df.Pclass.unique()
```
### OUTPUT:

<img width="307" height="54" alt="image" src="https://github.com/user-attachments/assets/38a70013-2258-4d41-a06e-07dba03c2c8b" />

## RENAMING COLUMN:
```PYTHON
df.rename(columns = {'Sex':'Gender'}, inplace = True)
df
```
### OUTPUT:

<img width="1355" height="502" alt="image" src="https://github.com/user-attachments/assets/cce743fc-294a-482c-a322-49f934cb0486" />

## BIVARIATE ANALYSIS:
## USE CATPLOT METHOD FOR BIVARIATE ANALYSIS:
```PYTHON
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
### OUTPUT:

<img width="899" height="683" alt="image" src="https://github.com/user-attachments/assets/bd8a112b-0e3d-490c-979b-e8053da8f31e" />


## KDE PLOT (JOINT DISTRIBUTION):
```PYTHON
sns.kdeplot(x='Survived', y='Age', data=df, cmap="Blues", shade=True)
plt.title('Bivariate KDE Plot')
plt.show()
```
### OUTPUT:

<img width="754" height="652" alt="image" src="https://github.com/user-attachments/assets/146b56b4-3f0f-4b3a-b3b1-5697c1b451d6" />

## REGRESSION PLOT FOR LINEAR RELATIONSHIPS:
```PYTHON
sns.lmplot(x='Survived', y='Age', data=df)
plt.title('Regression Plot: Numerical Column 1 vs Numerical Column 2')
plt.show()
```

### OUTPUT:

<img width="729" height="675" alt="image" src="https://github.com/user-attachments/assets/c02d80d9-23ee-4228-acce-e00afc5955e0" />


## USE BOXPLOT METHOD TO ANALYZE AGE AND SURVIVED COLUMN:
```PYTHON
df.boxplot(column="Age",by="Survived")
```

### OUTPUT:

<img width="797" height="657" alt="image" src="https://github.com/user-attachments/assets/4d7b7506-7469-46df-9385-0c27a8b3d558" />

## USE SCATTERPLOT OF COLUMN AGE AND FARE:
```PYTHON
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

### OUTPUT:

<img width="826" height="630" alt="image" src="https://github.com/user-attachments/assets/218ae799-97df-461c-b163-45946029f5b4" />

## USE JOINTPLOT COLUMN AGE AND FARE:
```PYTHON
sns.jointplot(x="Age",y="Fare",data=df)
```
### OUTPUT:

<img width="780" height="803" alt="image" src="https://github.com/user-attachments/assets/a85cc3bf-0417-45a5-953d-952906523c1e" />


## VIOLIN PLOT FOR COMBINED DISTRIBUTION AND RANGE:
```PYTHON
sns.violinplot(x='Gender', y='Survived', data=df)
plt.title('Violin Plot: Numerical vs Categorical')
plt.show()
```

### OUTPUT:

<img width="768" height="625" alt="image" src="https://github.com/user-attachments/assets/0f53d95a-84f0-4da8-8926-dc6e4b4938a0" />

## MULTIVARIATE ANALYSIS:
## USE BOXPLOT METHOD AND ANALYZE THREE COLUMNS(PCLASS,AGE,GENDER):
```PYTHON
fig, ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
### OUTPUT:

<img width="886" height="585" alt="image" src="https://github.com/user-attachments/assets/951d0b6e-27fb-4a6a-8089-d802c501873d" />


## USE CATPLOT METHOD AND ANALYZE THREE COLUMNS(PCLASS,SURVIVED,GENDER):
```PYTHON
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

### OUTPUT:

!<img width="1336" height="713" alt="image" src="https://github.com/user-attachments/assets/410d5f4d-6e0d-48a1-9697-ae88e26e2fec" />


## CO-RELATION:
```PYTHON
corr=df.corr()
sns.heatmap(corr,annot=True)
```

### OUTPUT:

<img width="732" height="603" alt="image" src="https://github.com/user-attachments/assets/bbb1e3d7-e987-4bd6-b2a4-10d9c9bbfef8" />


## IMPLEMENT HEATMAP AND PAIRPLOT FOR THE DATASET:
```PYTHON
sns.pairplot(df)
```

### OUTPUT:

<img width="975" height="907" alt="image" src="https://github.com/user-attachments/assets/da074335-1d4b-441f-89e3-7fe6ce72ff61" />


# RESULT
Hence performing Exploratory Data Analysis on the given data set is successfully executed.

