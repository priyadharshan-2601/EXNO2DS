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

df=pd.read_csv("titanic_dataset.csv")

from google.colab import drive
drive.mount('/content/drive')

df
<img width="1460" height="463" alt="image" src="https://github.com/user-attachments/assets/ffbe8555-d96f-46a7-88e5-dd6247d47f97" />

df.info()
<img width="425" height="417" alt="image" src="https://github.com/user-attachments/assets/0842fa4e-3f2c-49af-9258-0db577742192" />

df.shape
<img width="106" height="31" alt="image" src="https://github.com/user-attachments/assets/a475c1ad-7f0e-4dd4-a556-8129057aea87" />

df.set_index("PassengerId",inplace=True)
df.describe()
<img width="871" height="352" alt="image" src="https://github.com/user-attachments/assets/ee9c1be5-066c-4bb3-aa6e-b56c202275c6" />

df.shape
<img width="397" height="207" alt="image" src="https://github.com/user-attachments/assets/d359d7bf-e02e-4751-ba8a-b958d7c2a683" />

df.nunique()
<img width="163" height="467" alt="image" src="https://github.com/user-attachments/assets/abb25b00-f378-4595-8bdb-ce4a736683a8" />

df["Survived"].value_counts()
<img width="167" height="148" alt="image" src="https://github.com/user-attachments/assets/0cfc583c-7f90-480d-bf7e-8c74e3253863" />

per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
<img width="170" height="160" alt="image" src="https://github.com/user-attachments/assets/19ee6daa-63b6-4fdf-b1ac-3330b7c7cc9a" />

sns.countplot(data=df,x="Survived")
<img width="733" height="572" alt="image" src="https://github.com/user-attachments/assets/490b96c5-a309-45f2-9872-27e3950c1d85" />

df
<img width="1416" height="527" alt="image" src="https://github.com/user-attachments/assets/249ac214-3eb6-434b-b731-32db6bc62478" />

df.Pclass.unique()
<img width="171" height="36" alt="image" src="https://github.com/user-attachments/assets/7f89e1a7-d5c1-4a60-b78e-d56aac7c2230" />

df.rename(columns={'Sex':'Gender'},inplace=True)
df
<img width="1426" height="512" alt="image" src="https://github.com/user-attachments/assets/60e19338-1458-4085-8086-58288ecff5b5" />

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
<img width="898" height="648" alt="image" src="https://github.com/user-attachments/assets/7b9c1727-f815-4f5d-9d4f-e88535054763" />

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
<img width="745" height="643" alt="image" src="https://github.com/user-attachments/assets/0e1ba12d-7045-42ff-baf2-8968579d8a43" />

df.boxplot(column="Age",by="Survived")
<img width="717" height="608" alt="image" src="https://github.com/user-attachments/assets/8174abb9-58fb-4ff7-bfa2-ccefcd020a15" />

sns.scatterplot(x=df["Age"],y=df["Fare"])
<img width="730" height="580" alt="image" src="https://github.com/user-attachments/assets/b7f7a11b-f845-425c-b419-1f7d746513e4" />

sns.jointplot(x="Age",y="Fare",data=df)
<img width="760" height="725" alt="image" src="https://github.com/user-attachments/assets/a3d019ec-165c-444f-ad37-8220adec4af0" />

fig, ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x='Pclass', y='Age', hue='Gender', data=df)
<img width="872" height="596" alt="image" src="https://github.com/user-attachments/assets/d2a3cfd5-63e2-436a-86a5-64bcf1fc0361" />

plt.show()
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
<img width="1333" height="643" alt="image" src="https://github.com/user-attachments/assets/4a681518-425b-496e-ac82-3f80a2db0692" />

corr = df.corr(numeric_only=True)
sns.heatmap(corr, annot=True)
<img width="677" height="552" alt="image" src="https://github.com/user-attachments/assets/10d977a6-83aa-4a2d-9d87-0f2087fbab37" />

sns.pairplot(df)
<img width="738" height="777" alt="image" src="https://github.com/user-attachments/assets/0230788b-6671-43d4-8bff-1d643be6f5d7" />

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
