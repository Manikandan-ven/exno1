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
```











# Result
          <<include your Result here>>
