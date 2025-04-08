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
~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
~~~
![Screenshot 2025-03-25 133524](https://github.com/user-attachments/assets/04fbcf65-fd80-4108-ad86-6cc026b8a49b)
~~~
df.info()
~~~
![Screenshot 2025-03-25 133534](https://github.com/user-attachments/assets/aa3fbbd0-6662-4ed4-aad8-f9bfb1100b1a)
~~~
df.shape
~~~
![Screenshot 2025-03-25 133542](https://github.com/user-attachments/assets/2a4fd621-4de9-4f64-9a51-fb351ae58d5b)
~~~
df.set_index("PassengerId",inplace=True)
df.describe()
~~~
![Screenshot 2025-03-25 133549](https://github.com/user-attachments/assets/ca6d07ee-6047-48db-b5c3-564bb12fc8a0)
~~~
df.shape
~~~
![Screenshot 2025-03-25 133556](https://github.com/user-attachments/assets/cc3aae99-7bd9-464f-8f2a-b14e344374a5)
~~~
df.nunique()
~~~
![Screenshot 2025-03-25 133601](https://github.com/user-attachments/assets/49080eff-983d-4c1d-9881-96bd4b4dfddc)
~~~
df["Survived"].value_counts()
~~~
![Screenshot 2025-03-25 133608](https://github.com/user-attachments/assets/72b5dbca-a14a-4454-8dde-ada968816ee0)
~~~
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
~~~
![Screenshot 2025-03-25 133614](https://github.com/user-attachments/assets/0720ab06-f111-4f3f-815e-3b55d7d92374)
~~~
sns.countplot(data=df,x="Survived")
~~~
![Screenshot 2025-03-25 133620](https://github.com/user-attachments/assets/24f366ed-b9a9-4afa-b6e7-c34c489b3f64)
~~~
df
~~~
![Screenshot 2025-03-25 133631](https://github.com/user-attachments/assets/369a4f22-f7e7-4388-a5c5-61092efdc108)
~~~
df.Pclass.unique()
~~~
![Screenshot 2025-03-25 133641](https://github.com/user-attachments/assets/55821999-b775-4b97-a0bb-6eb15d76ab6e)
~~~
df.rename(columns={'Sex':'Gender'},inplace=True)
df
~~~
![Screenshot 2025-03-25 133651](https://github.com/user-attachments/assets/fcb76d41-6a07-4723-a54b-9cc14f15d40b)
~~~
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
~~~
![Screenshot 2025-03-25 133700](https://github.com/user-attachments/assets/6bae3096-0584-447c-8b12-3c179cc51b9d)
~~~
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
~~~
![Screenshot 2025-03-25 133708](https://github.com/user-attachments/assets/dbdd0705-1639-4b2d-96e0-c43a39ef77c1)
~~~
df.boxplot(column="Age",by="Survived")
~~~
![Screenshot 2025-03-25 133720](https://github.com/user-attachments/assets/2b8f2d32-fd53-4bef-b4cf-fa1dd06c2c18)
~~~
sns.scatterplot(x=df["Age"],y=df["Fare"])
~~~
![Screenshot 2025-03-25 133921](https://github.com/user-attachments/assets/44ba9006-9bb4-4f09-bfd7-9dd4603d3bab)
~~~
sns.jointplot(x="Age",y="Fare",data=df)
~~~
![Screenshot 2025-03-25 133929](https://github.com/user-attachments/assets/61687759-c489-403d-a929-7ddcca64cddf)
~~~
fig, ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
~~~
![Screenshot 2025-03-25 133936](https://github.com/user-attachments/assets/ae96e686-1b48-4006-9642-1518103afd80)
~~~
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
~~~
![Screenshot 2025-03-25 133947](https://github.com/user-attachments/assets/7401d9d1-0885-4be8-bad6-5de1e36a0a70)
~~~
corr = df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
~~~
![Screenshot 2025-03-25 133955](https://github.com/user-attachments/assets/1df402b5-1697-4074-8bcf-bec11ac58398)
~~~
sns.pairplot(df)
~~~
![Screenshot 2025-03-25 134138](https://github.com/user-attachments/assets/f1524fa6-d9d0-47b9-8a22-728805cc1ef3)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
