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
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df

<img width="1358" height="780" alt="Screenshot 2025-09-15 113025" src="https://github.com/user-attachments/assets/31d7c489-f76e-4271-a12c-be2a0cee2175" />

df.info()

<img width="696" height="517" alt="Screenshot 2025-09-15 113038" src="https://github.com/user-attachments/assets/e6e1e551-09b3-463e-9907-1644d03b71df" />

df.describe()

<img width="957" height="439" alt="Screenshot 2025-09-15 113049" src="https://github.com/user-attachments/assets/2a32168c-b84b-4f2d-9cd6-99c06bd528be" />

df.dtypes

<img width="849" height="650" alt="Screenshot 2025-09-15 113100" src="https://github.com/user-attachments/assets/ad7c50a0-81dd-4d16-82b7-76a3b8232d5f" />

df.shape

<img width="779" height="112" alt="Screenshot 2025-09-15 113225" src="https://github.com/user-attachments/assets/c42c6fdc-0829-4c44-a442-d054c63a8269" />

df.value_counts()

<img width="1407" height="766" alt="Screenshot 2025-09-15 113313" src="https://github.com/user-attachments/assets/91435e87-ee45-4c03-bfd1-7028527811d9" />

df['Age'].value_counts()

<img width="866" height="672" alt="Screenshot 2025-09-15 113323" src="https://github.com/user-attachments/assets/3f2928cf-ab8c-4d2b-820f-2f2a755013d2" />

df.reset_index(inplace=True)
df.set_index("PassengerId",inplace=True)
df

<img width="1446" height="810" alt="Screenshot 2025-09-15 113336" src="https://github.com/user-attachments/assets/d3b2cf00-b945-4cc9-b3a7-e2dd75e5b748" />

df.nunique()

<img width="995" height="676" alt="Screenshot 2025-09-15 113344" src="https://github.com/user-attachments/assets/dd9226f0-eb9e-48ca-b3ab-43a20c6fcda2" />

sns.countplot(data=df,x='Age')

<img width="999" height="642" alt="Screenshot 2025-09-15 113353" src="https://github.com/user-attachments/assets/0324d834-a593-44a4-8ebf-90caca74f5f0" />

df.rename(columns={'Sex':'Gender'},inplace=True)
df


<img width="1395" height="760" alt="Screenshot 2025-09-15 113407" src="https://github.com/user-attachments/assets/aee0d35a-68ad-48ef-8a23-8bf98270b979" />
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=0.7)


<img width="1047" height="729" alt="Screenshot 2025-09-15 113420" src="https://github.com/user-attachments/assets/cc79013c-7d3c-47d4-85e9-df3e10043f6b" />

df.boxplot(column="Age",by="Survived")


<img width="934" height="676" alt="Screenshot 2025-09-15 113430" src="https://github.com/user-attachments/assets/1341539f-85e7-44c6-9579-6022daaea425" />

sns.scatterplot(x=df["Age"],y=df["Fare"])


<img width="934" height="637" alt="Screenshot 2025-09-15 113436" src="https://github.com/user-attachments/assets/61612e24-0c8a-403e-a85b-9a497349b9ca" />

sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)

<img width="923" height="636" alt="Screenshot 2025-09-15 113443" src="https://github.com/user-attachments/assets/1b71c84a-69da-487b-9a46-ac9fadbc9dae" />

sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind='box',data=df)

<img width="1487" height="716" alt="Screenshot 2025-09-15 113454" src="https://github.com/user-attachments/assets/7d9abe95-7278-4b9c-accc-28e449e1c5fe" />

corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot =True)

<img width="1009" height="716" alt="Screenshot 2025-09-15 113500" src="https://github.com/user-attachments/assets/ef4ecdda-6794-4539-85da-749bb65505f2" />

corr=df.corr(numeric_only=True)
sns.heatmap(corr)

<img width="1003" height="705" alt="Screenshot 2025-09-15 113509" src="https://github.com/user-attachments/assets/05281dbf-24c3-4d40-8f29-a5e145941297" />
# RESULT
Thus the program was successfully verified and done.
