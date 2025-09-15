# EXP.NO. :1 - Data Cleaning Process

# AIM :
To read the given data and perform data cleaning and save the cleaned data to a file.

# EXPLANATION:
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# ALGORITHM :
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# CODING AND OUTPUT :
```
import pandas as pd 
df = pd.read_csv("Data_set.csv")
print(df)
```
<img width="644" height="704" alt="image" src="https://github.com/user-attachments/assets/7e47e389-ac32-40fe-8214-425833619973" />

```
df.describe()
```

<img width="727" height="288" alt="image" src="https://github.com/user-attachments/assets/d9a2578c-cfaa-4433-81b6-5ce1cb022fea" />

```
df.info()
```
<img width="443" height="294" alt="Screenshot 2025-09-03 140010" src="https://github.com/user-attachments/assets/ac32d999-f4f1-4123-a933-eba70fda9f23" />

```
df.head(4)
```
<img width="1191" height="168" alt="Screenshot 2025-09-03 140109" src="https://github.com/user-attachments/assets/8f4209d1-df0f-45cb-8cfa-b50296d1b538" />

```
df.tail(3)
```
<img width="1171" height="134" alt="Screenshot 2025-09-03 140158" src="https://github.com/user-attachments/assets/343e7c32-6427-4453-a75d-14622cda2834" />

```
df.isnull()
```
<img width="1031" height="404" alt="image" src="https://github.com/user-attachments/assets/fe2d4426-aee9-4689-8c63-db447c8bb1af" />

```
df.notnull()
```
<img width="1020" height="398" alt="image" src="https://github.com/user-attachments/assets/d758ec39-530c-4ecd-9b18-b3279209f929" />

```
df.isnull().sum()
```
<img width="216" height="347" alt="image" src="https://github.com/user-attachments/assets/863cc90d-9e3a-4abb-9965-b1ec38009441" />

```
df.notnull().sum()
```
<img width="234" height="350" alt="image" src="https://github.com/user-attachments/assets/0119dd7a-4ebd-44a4-be67-d454707ce92c" />

```
df.shape
```
<img width="85" height="33" alt="image" src="https://github.com/user-attachments/assets/bea2e3a3-1a58-4210-9405-92d320b3b765" />

```
df[df['rating'] > 8]
```
<img width="1236" height="403" alt="image" src="https://github.com/user-attachments/assets/6d68cb82-898c-4a24-b178-5f1ca7fa3a6b" />

```
df[df['num_episodes'] > 20]
```
<img width="1422" height="515" alt="Screenshot 2025-09-03 140619" src="https://github.com/user-attachments/assets/9b59f147-0779-475b-877a-5faa76760815" />

```
df.iloc[2:5 , :-3]
```
<img width="750" height="151" alt="image" src="https://github.com/user-attachments/assets/c230dde8-ad48-4942-951a-b2f270a7f0b3" />

```
df.iloc[[6,7,8],[1,2,3]]
```
<img width="389" height="135" alt="image" src="https://github.com/user-attachments/assets/3d277e0f-e816-4cf4-85c6-7199670fd531" />

```
df.loc[3:5 , ['country' , 'num_episodes']]
```
<img width="232" height="134" alt="image" src="https://github.com/user-attachments/assets/6feffc6d-d06f-4a22-9443-affbaad4d771" />

```
df['country'].value_counts()
```
<img width="179" height="205" alt="image" src="https://github.com/user-attachments/assets/28e1c6fd-23fe-4788-b427-930f29a960ef" />

```
df.count()
```
<img width="235" height="359" alt="image" src="https://github.com/user-attachments/assets/a6ce066d-3c82-450a-afbb-acdda6bfac4d" />

```
df.dropna(axis = 1)
```
<img width="445" height="413" alt="image" src="https://github.com/user-attachments/assets/980bed84-924c-442f-8c08-44b38309e3d9" />

```
df.fillna(0)
```
<img width="1217" height="403" alt="Screenshot 2025-09-03 141030" src="https://github.com/user-attachments/assets/037551f7-d1c2-4467-9d0d-12d42ad548b3" />

```
df.fillna(method = 'bfill')
```
<img width="1213" height="394" alt="image" src="https://github.com/user-attachments/assets/2d1f7b0a-fd8e-438a-8fd8-230974d34d92" />

```
df.interpolate()
```
<img width="1222" height="397" alt="image" src="https://github.com/user-attachments/assets/adf52629-599d-4477-80f0-fdc51695bf80" />

```
ffil = df.fillna(method = 'ffill')
print(ffil)
```
<img width="616" height="707" alt="image" src="https://github.com/user-attachments/assets/d0d6f9b6-4dad-4b66-993d-10892f0d7475" />

```
bfil = df.fillna(method = 'bfill')
print(bfil)
```
<img width="637" height="698" alt="image" src="https://github.com/user-attachments/assets/e102dd73-cadd-43a3-a350-46e86181b61b" />

```
m = df.num_episodes.mean()
print(m)
```
<img width="53" height="26" alt="image" src="https://github.com/user-attachments/assets/c84672ce-bf14-46ec-abb7-2669762507f3" />

```
m = df.fillna(df['num_episodes'].mean())
print(m)
```
<img width="631" height="702" alt="image" src="https://github.com/user-attachments/assets/00684a5e-0e43-418f-9c69-e4b19bf3d87c" />

```
fmean = df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
print(fmean)
```
<img width="461" height="228" alt="image" src="https://github.com/user-attachments/assets/06458e0a-5995-4257-96ae-f3cc6c0bad39" />

```
df = pd.read_csv('SAMPLEIDS.csv')
print(df)
```
<img width="615" height="801" alt="image" src="https://github.com/user-attachments/assets/88433bae-64be-43bb-b346-90be03fa2f98" />

```
df['GENDER'].value_counts()
```
<img width="153" height="186" alt="image" src="https://github.com/user-attachments/assets/9c55efd1-ad59-4a31-8987-600348ebf9d4" />

```
x1 = df.dropna(how='any')
print(x1)
```
<img width="631" height="513" alt="image" src="https://github.com/user-attachments/assets/9c0b8117-8ac4-418d-8908-dd3b3369c09b" />

```
res = df.dropna(subset=['M1','M2','M3','M4'],how='any') 
print(res)
```
<img width="614" height="525" alt="image" src="https://github.com/user-attachments/assets/004bfd3f-0024-45d9-a78b-dddc10084443" />

```
df=pd.read_csv('heights.csv')
print(df)
```
<img width="172" height="277" alt="image" src="https://github.com/user-attachments/assets/8199b212-6bd9-4c50-9048-f2e3f20240b1" />

```
import seaborn as sns
import matplotlib.pyplot as plt

sns.boxplot(data=df)
plt.show()
```
<img width="564" height="426" alt="image" src="https://github.com/user-attachments/assets/322e146d-4312-4b81-956c-c744e2838d18" />

```
sns.scatterplot(data=df)
```
<img width="559" height="444" alt="image" src="https://github.com/user-attachments/assets/f7b9be59-74b5-4b8e-af5f-f0f32323e08c" />

```
q3 = df["height"].quantile(0.75)
q1 = df["height"].quantile(0.25)
iqr = q3 - q1
print(iqr)
```
<img width="163" height="32" alt="image" src="https://github.com/user-attachments/assets/db99504d-1553-482f-b64e-4cb0cf7f266b" />

```
q1, q3 = df["height"].quantile([0.25, 0.75])
iqr = q3 - q1
lb, ub = q1 - 1.5*iqr, q3 + 1.5*iqr
outliers = df[(df["height"] < lb) | (df["height"] > ub)]

print(f"Lower bound: {lb}\nUpper bound: {ub}\nOutliers:\n{outliers}")
```
<img width="257" height="126" alt="image" src="https://github.com/user-attachments/assets/d5ea8731-74e5-4496-9d44-1e179346add6" />

```
import numpy as np
from scipy import stats

z = np.abs(stats.zscore(df["height"]))
z = pd.Series(z, name="height")   # make it a Series with name
print(z)

```
<img width="233" height="278" alt="image" src="https://github.com/user-attachments/assets/90aab726-109f-4fed-ac45-5c2d7001412e" />

```
df1 = df[z<3]
print(df1)
```
<img width="166" height="251" alt="image" src="https://github.com/user-attachments/assets/662d67aa-2f30-4924-8684-61e366ca5a8b" />

# SUMMERY:

Use head, tail, describe, info to understand dataset structure.

Apply isnull, notnull, sum to find missing values.

Extract rows/columns using labels, indices, or conditions.

Handle missing data by drop, fill, interpolate, or mean/median/mode imputation.

Use value_counts to check category frequencies.

Merge, join, or concatenate multiple datasets.

Plot boxplot or scatterplot to visualize data distributions.

Detect and remove outliers using IQR or Z-score methods.

# RESULT :
Thus the given data has been read, cleaned and the data has been saved to a file.
