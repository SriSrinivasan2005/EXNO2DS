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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="1481" height="708" alt="Screenshot 2025-09-16 103238" src="https://github.com/user-attachments/assets/5894be55-acd9-49c7-9256-ea7692b02f96" />

```
df.info()
```
<img width="885" height="481" alt="Screenshot 2025-09-16 103247" src="https://github.com/user-attachments/assets/e59ad21e-d8ae-42d4-a709-321b3c556dbe" />

```
df.describe()
```
<img width="1074" height="425" alt="Screenshot 2025-09-16 103255" src="https://github.com/user-attachments/assets/ff135547-8c5a-4f14-a534-130554e1ed3d" />

```
df.dtypes
```
<img width="756" height="619" alt="Screenshot 2025-09-16 103307" src="https://github.com/user-attachments/assets/d8cc82e8-0c70-4ec1-86b0-9daa3894cd9f" />

```
df.value_counts()
```
<img width="1558" height="642" alt="Screenshot 2025-09-16 103322" src="https://github.com/user-attachments/assets/de68f68f-09f6-4621-8c33-d241fe90533f" />

```
df['Age'].value_counts()
```
<img width="633" height="656" alt="Screenshot 2025-09-16 103332" src="https://github.com/user-attachments/assets/2de6ceff-8666-48e7-8d15-dab536813297" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="988" height="441" alt="Screenshot 2025-09-16 103339" src="https://github.com/user-attachments/assets/becf9ac0-d5fb-4302-ace5-d3141ff03536" />

```
df.shape
```
<img width="469" height="111" alt="Screenshot 2025-09-16 103346" src="https://github.com/user-attachments/assets/55a9e3c4-f983-4992-ae90-f47c014cc065" />

```
df.nunique()
```
<img width="715" height="592" alt="Screenshot 2025-09-16 103456" src="https://github.com/user-attachments/assets/409ba395-cd32-420c-8a41-31695703f6be" />

```
sns.countplot(x='Survived',data=df)
```
<img width="863" height="615" alt="Screenshot 2025-09-16 103505" src="https://github.com/user-attachments/assets/82b0d37e-2f1e-48bc-8c45-09d94421679a" />

```
df.Pclass.unique()
```
<img width="465" height="111" alt="Screenshot 2025-09-16 103512" src="https://github.com/user-attachments/assets/710f3feb-e3bc-4179-9315-82c41c252fc0" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1444" height="640" alt="Screenshot 2025-09-16 103529" src="https://github.com/user-attachments/assets/d0068479-0149-4f3e-bbac-bca6e0211a4b" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=7,aspect=.7)
```
<img width="1101" height="773" alt="Screenshot 2025-09-16 103550" src="https://github.com/user-attachments/assets/20e10b4d-32ee-4602-a0ca-edebbee4880f" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="836" height="595" alt="Screenshot 2025-09-16 103601" src="https://github.com/user-attachments/assets/00a2943e-d184-4839-a804-970476143a67" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="811" height="578" alt="Screenshot 2025-09-16 103607" src="https://github.com/user-attachments/assets/e7f13802-c0ac-4ece-b3c7-977d9e28215a" />

```
fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="920" height="588" alt="Screenshot 2025-09-16 103615" src="https://github.com/user-attachments/assets/e7b0c1ca-c592-452a-9cb2-86d1370c1f39" />

```
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="817" height="540" alt="Screenshot 2025-09-16 103621" src="https://github.com/user-attachments/assets/35ad14ba-03b6-41a2-a710-f972cd88f861" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1265" height="634" alt="Screenshot 2025-09-16 103628" src="https://github.com/user-attachments/assets/ca9aa0c0-e286-4f6f-9eb5-5054ad9dd90c" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
<img width="785" height="577" alt="Screenshot 2025-09-16 103636" src="https://github.com/user-attachments/assets/e0162b85-e7b3-4409-8eea-0d1fe5d9ab5d" />


       
## RESULT
Thus exploratory data analysis on the given data set has been executed successfully      
