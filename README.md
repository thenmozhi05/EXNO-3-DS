## EXNO-3-DS

# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:
```
    import pandas as pd
    df=pd.read_csv("/content/Encoding Data (1).csv")
    df
```
![image](https://github.com/user-attachments/assets/4d7590a3-7845-481c-b76a-63c6b52df881)

```
     from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
     pm=['Hot','Warm','Cold']
     e1=OrdinalEncoder(categories=[pm])
     e1.fit_transform(df[["ord_2"]])
```
![image](https://github.com/user-attachments/assets/00c9afd3-9657-4012-9bab-4290dee056d1)
```
    df['bo2']=e1.fit_transform(df[["ord_2"]])
```
![image](https://github.com/user-attachments/assets/2fc4d442-5525-4ea7-bf88-a7f14745f3c3)
```
     le=LabelEncoder()
     dfc=df.copy()
     dfc['ord_2']=le.fit_transform(dfc['ord_2'])
```
![image](https://github.com/user-attachments/assets/42b86563-b895-449e-8b22-9add81274f9d)
```
      from sklearn.preprocessing import OneHotEncoder
       ohe=OneHotEncoder(sparse=False)
       df2=df.copy()
       enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
```
![image](https://github.com/user-attachments/assets/4c3c25d6-061b-4c7d-9ce6-ca739043e85d)
```
      df2=pd.concat([df2,enc],axis=1)
```
![image](https://github.com/user-attachments/assets/2f8c4af3-32eb-452c-83d6-3afcf805b5fd)
![image](https://github.com/user-attachments/assets/d2568e5c-9bf9-46f0-9a71-9f30fc246a3a)
```
         from category_encoders import BinaryEncoder
         df=pd.read_csv("/content/data.csv")
         be=BinaryEncoder()
         nd=be.fit_transform(df['Ord_2'])
         dfb=pd.concat([df,nd],axis=1)
         dfb1=df.copy()
```
![image](https://github.com/user-attachments/assets/d2310938-b19f-4e7b-b187-3d80809c49e1)
```
         from category_encoders import TargetEncoder
         te=TargetEncoder()
         cc=df.copy()
         new=te.fit_transform(X=cc["City"],y=cc["Target"])
         cc=pd.concat([cc,new],axis=1)
```
![image](https://github.com/user-attachments/assets/6492928b-3089-4c05-a2a5-82ce039b9ad3)
![image](https://github.com/user-attachments/assets/81b8db91-09bf-48a9-973a-7a92ae0bead8)
![image](https://github.com/user-attachments/assets/957a6034-8acf-4023-9678-9fbf42898d9b)
![image](https://github.com/user-attachments/assets/f2712f17-b2c4-415b-a494-ddae136b8571)
![image](https://github.com/user-attachments/assets/0eaacf5b-9e09-423e-a9b2-aa73319d6ecf)
```
df["Higly Positive Skew_borcox"],parameters=stats.boxcox(df["Highly Positive Skew"])
```
![image](https://github.com/user-attachments/assets/2b20b086-b1df-4154-a2f4-172927ffbca2)
```
df["Highly Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Highly Negative Skew"])
```
![image](https://github.com/user-attachments/assets/abf19cd1-8e06-492c-89fe-e4f8ae1f7225)
```
         from sklearn.preprocessing import QuantileTransformer
         qt=QuantileTransformer(output_distribution='normal')
```
![image](https://github.com/user-attachments/assets/0a8ef01f-d920-4df9-9d39-64759e4ea9ee)
![image](https://github.com/user-attachments/assets/3937bc9a-9d94-452e-a206-7e52e369a59d)
![image](https://github.com/user-attachments/assets/f380d388-de12-444e-8ae9-3ef20747198b)
![image](https://github.com/user-attachments/assets/998a768c-b896-47a6-885e-658b62c690b7)
![image](https://github.com/user-attachments/assets/9e77f0cb-0e44-45db-aa29-d6ad29375fc0)
![image](https://github.com/user-attachments/assets/92f2f42e-ec13-4082-9508-bc2be12d321c)
![image](https://github.com/user-attachments/assets/1a5f5824-95f4-4667-8243-df61f392bd07)


# RESULT:
   Thus To read the given data and perform Feature Encoding and Transformation process and save the data to a file has successfully executed  

       
