# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
# DATA CLEANING
```
import pandas as pd
data=pd.read_csv("/content/Data_set.csv")
data.head(7)
```
![image](https://github.com/user-attachments/assets/a6c29032-b226-450a-a637-2698ada706d8)
```
data.tail()
```
![Screenshot 2025-03-04 110028](https://github.com/user-attachments/assets/c3e3012f-23f4-4d16-bb56-e00e5be14fe7)
```
data.isnull()
```
![image](https://github.com/user-attachments/assets/db2f8936-e9d1-49f7-a2f5-44e547d87b5e)
```
data.notnull()
```
![image](https://github.com/user-attachments/assets/6cc691a1-7c16-48ff-b59e-9a0211e39da4)
```
data.fillna(400)
```
![image](https://github.com/user-attachments/assets/12e854a1-cc24-4085-970d-1b14d2fc2c5c)
```
data.dropna()
```
![image](https://github.com/user-attachments/assets/e59fd9cf-2ab5-4e83-a44f-d0e5a9635b12)
```
data.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/c97d6d0f-d6a0-4664-ac3a-11645885ea7f)
```
data.dropna(axis=1)
```
![image](https://github.com/user-attachments/assets/000fefc8-8b91-4fcb-bc32-ddfb577b4bac)
```
data.describe()
```
![image](https://github.com/user-attachments/assets/429e9ae4-8e69-4f8b-9219-2f04556e13a2)
```
data.shape
```
![image](https://github.com/user-attachments/assets/8a716658-0adb-4acb-84b5-05a66fb08300)
```
data.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/9bafc610-ebd9-4bd8-9d15-9f3db9b90188)
```
data.fillna(method='bfill')
```
![Screenshot 2025-03-04 112501](https://github.com/user-attachments/assets/14a59b70-a96e-42d4-ba7b-5ab88c257448)
```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/e4b25674-cbe6-4933-835f-1651b9e9acbf)
```
data.isnull().any()
```
![image](https://github.com/user-attachments/assets/db3a889a-de66-4690-980a-1bc1af7dd142)


#IQR(inter quartile range)
```
ir=pd.read_csv("/content/iris.csv")
df
```
![image](https://github.com/user-attachments/assets/c4f255bd-4fcc-4072-aafc-7f60b16c22cd)
```
ir.describe()
```
![image](https://github.com/user-attachments/assets/f3c01840-1df8-4102-a5ac-9ae1a24a6b2d)


```
import seaborn as sns
sns.boxplot(x='sepal_width' ,data=df)
```
![image](https://github.com/user-attachments/assets/02c93958-39b4-47c9-9d12-99cb2e789065)
```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
![image](https://github.com/user-attachments/assets/737a5010-52c8-4ae8-a2ea-4639a76ec9c2)
```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/49a3c808-b44d-40a2-84a4-d6e299d5c088)
```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![image](https://github.com/user-attachments/assets/1f6ad030-d40e-48a2-81bc-01353bf6cc35)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/user-attachments/assets/af06529f-304d-451d-812b-6d1b6e37b1ea)
# z-score
```
import pandas as pd
import scipy.stats as stats
import numpy as np
df=pd.read_csv("/content/heights.csv")
df
```
![image](https://github.com/user-attachments/assets/56cdb980-61d5-4f05-855f-0960e2cb4f10)

```
z=np.abs(stats.zscore(df['height']))
z
```
![image](https://github.com/user-attachments/assets/b98b2eaa-e5d3-441b-a32a-93ae45b65407)
```
df = pd.read_csv("heights.csv")
 q1 = df['height'].quantile(0.25)
 q2 = df['height'].quantile(0.5)
 q3 = df['height'].quantile(0.75)
 iqr = q3-q1
 iqr
 
```
![image](https://github.com/user-attachments/assets/df46e4ad-13f6-477d-b28c-c82fffb930ac)

```
low = q1- 1.5*iqr
 low
 
```
![image](https://github.com/user-attachments/assets/5ac9f459-90eb-439f-868e-39067489b2a4)
```
 high = q3 + 1.5*iqr
 high

```
![image](https://github.com/user-attachments/assets/d503bf31-edbb-4b2f-8f81-3dc694fd2e0f)
```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![image](https://github.com/user-attachments/assets/1cc0c36d-ff2f-4185-a08e-a29b1b0768ee)
```
 z = np.abs(stats.zscore(df['height']))
 z
```
![image](https://github.com/user-attachments/assets/e6ca6216-272d-43f8-9f4e-d170c2cd689c)
```
df1 = df[z<3]
 df1
```
![image](https://github.com/user-attachments/assets/c6fd0e54-a7cf-46e2-8a47-930af4de9d28)



# Result
          Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method
