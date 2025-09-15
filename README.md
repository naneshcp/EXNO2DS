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
        <<INCLUDE YOUR CODING AND OUTPUT SCREENSHOTS>>

import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
<img width="1358" height="780" alt="Screenshot 2025-09-15 113025" src="https://github.com/user-attachments/assets/f043e654-425d-4bfc-a0a6-46bdbfc17571" />


df.info()
<img width="696" height="517" alt="Screenshot 2025-09-15 113038" src="https://github.com/user-attachments/assets/1e17f813-3ab9-49f9-b989-9b5aa0ec5dd6" />


df.describe()
<img width="957" height="439" alt="Screenshot 2025-09-15 113049" src="https://github.com/user-attachments/assets/5df3e07e-30d7-48df-880a-5107b887f46a" />

df.dtypes
<img width="849" height="650" alt="Screenshot 2025-09-15 113100" src="https://github.com/user-attachments/assets/f3a8cdaf-9348-4e60-9828-a4342c79fa32" />

df.shape
<img width="779" height="112" alt="Screenshot 2025-09-15 113225" src="https://github.com/user-attachments/assets/95b94442-176e-4a7c-a738-162ed7a7f68f" />

df.value_counts()
<img width="1407" height="766" alt="Screenshot 2025-09-15 113313" src="https://github.com/user-attachments/assets/8c8ba306-c7c0-4ad1-8888-d2988ada6ad1" />

df['Age'].value_counts()
<img width="866" height="672" alt="Screenshot 2025-09-15 113323" src="https://github.com/user-attachments/assets/4f0894d9-7643-4828-96f4-7a0c551ed1c3" />

df.reset_index(inplace=True)
df.set_index("PassengerId",inplace=True)
df
<img width="1446" height="810" alt="Screenshot 2025-09-15 113336" src="https://github.com/user-attachments/assets/33d34d77-e7e9-4453-951c-47c5b5bb4f7e" />

df.nunique()

sns.countplot(data=df,x='Age')
<img width="999" height="642" alt="Screenshot 2025-09-15 113353" src="https://github.com/user-attachments/assets/c5d91264-346d-4f34-b059-c1a56059736a" />

df.rename(columns={'Sex':'Gender'},inplace=True)
df
<img width="1395" height="760" alt="Screenshot 2025-09-15 113407" src="https://github.com/user-attachments/assets/55e06708-9fb0-4b70-b29e-25053e1cedcf" />

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=0.7)
<img width="1047" height="729" alt="Screenshot 2025-09-15 113420" src="https://github.com/user-attachments/assets/913ed0a7-4676-435b-91e9-3c6b3b6a99a9" />

df.boxplot(column="Age",by="Survived")
<img width="934" height="676" alt="Screenshot 2025-09-15 113430" src="https://github.com/user-attachments/assets/a01aee68-c8e6-4ec1-aa17-95d67fb2fc2b" />

sns.scatterplot(x=df["Age"],y=df["Fare"])
<img width="934" height="637" alt="Screenshot 2025-09-15 113436" src="https://github.com/user-attachments/assets/405f33c7-79e9-40fd-bd6e-948e7b1b4a8a" />

sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
<img width="923" height="636" alt="Screenshot 2025-09-15 113443" src="https://github.com/user-attachments/assets/b1d018aa-8046-41fa-9e18-8839508c9c3a" />

sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind='box',data=df)
<img width="1487" height="716" alt="Screenshot 2025-09-15 113454" src="https://github.com/user-attachments/assets/65a9784b-d709-4d32-aafb-030c2604eebf" />

corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot =True)
<img width="1009" height="716" alt="Screenshot 2025-09-15 113500" src="https://github.com/user-attachments/assets/36b010f3-9e14-4da5-8be0-c55adcce1d46" />

corr=df.corr(numeric_only=True)
sns.heatmap(corr)
<img width="1003" height="705" alt="Screenshot 2025-09-15 113509" src="https://github.com/user-attachments/assets/b551ac90-df44-4fcf-9868-0db1ab090491" />


# RESULT
        <<INCLUDE YOUR RESULT HERE>>
Thus the program to perform Exploratory Data Analysis on the given data set successfully.
