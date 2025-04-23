# EXNO:4-DS
# AIM:
To read the given data and perform Feature Scaling and Feature Selection process and save the
data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Scaling for the feature in the data set.
STEP 4:Apply Feature Selection for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE SCALING:
1. Standard Scaler: It is also called Z-score normalization. It calculates the z-score of each value and replaces the value with the calculated Z-score. The features are then rescaled with x̄ =0 and σ=1
2. MinMaxScaler: It is also referred to as Normalization. The features are scaled between 0 and 1. Here, the mean value remains same as in Standardization, that is,0.
3. Maximum absolute scaling: Maximum absolute scaling scales the data to its maximum value; that is,it divides every observation by the maximum value of the variable.The result of the preceding transformation is a distribution in which the values vary approximately within the range of -1 to 1.
4. RobustScaler: RobustScaler transforms the feature vector by subtracting the median and then dividing by the interquartile range (75% value — 25% value).

# FEATURE SELECTION:
Feature selection is to find the best set of features that allows one to build useful models. Selecting the best features helps the model to perform well.
The feature selection techniques used are:
1.Filter Method
2.Wrapper Method
3.Embedded Method

# CODING AND OUTPUT:
```
import pandas as pd
from scipy import stats
import numpy as np
from sklearn.preprocessing import MinMaxScaler, StandardScaler, Normalizer, MaxAbsScaler, RobustScaler

df = pd.read_csv("/content/bmi.csv")

print(df.head())
```
![Screenshot 2025-04-23 154127](https://github.com/user-attachments/assets/d10ce31a-119a-4c4f-841a-caca2f1841b0)

```
df = df.dropna()

print("Max Height:", df["Height"].max())
print("Max Weight:", df["Weight"].max())
```
![Screenshot 2025-04-23 154131](https://github.com/user-attachments/assets/56f973ac-4c8d-4160-8d2a-13d9966e0538)


```
minmax = MinMaxScaler()
df_minmax = minmax.fit_transform(df[["Height", "Weight"]])
print("\nMinMaxScaler Result:\n", df_minmax[:5])
```
![Screenshot 2025-04-23 154135](https://github.com/user-attachments/assets/65bdc31d-cf12-4388-8ad5-bea242d95000)

```
standard = StandardScaler()
df_standard = standard.fit_transform(df[["Height", "Weight"]])
print("\nStandardScaler Result:\n", df_standard[:5])
```
![Screenshot 2025-04-23 154549](https://github.com/user-attachments/assets/8a6fd5e1-0c54-4bfe-a85b-cec1ea04db51)


```
normalizer = Normalizer()
df_normalized = normalizer.fit_transform(df[["Height", "Weight"]])
print("\nNormalizer Result:\n", df_normalized[:5])
```
![Screenshot 2025-04-23 154225](https://github.com/user-attachments/assets/8ebc5601-baaf-4a62-90d0-80717169de03)

```

max_abs = MaxAbsScaler()
df_maxabs = max_abs.fit_transform(df[["Height", "Weight"]])
print("\nMaxAbsScaler Result:\n", df_maxabs[:5])

```

![Screenshot 2025-04-23 154229](https://github.com/user-attachments/assets/2d4300cf-d8fb-4f20-ade3-6cd4ee595988)

```

robust = RobustScaler()
df_robust = robust.fit_transform(df[["Height", "Weight"]])
print("\nRobustScaler Result:\n",df_robust[:5])
```


![Screenshot 2025-04-23 154234](https://github.com/user-attachments/assets/66503976-4bbf-4ca8-9b9d-0bdf4e5a8719)


# RESULT:
       Feature Scaling and Feature selection process successfully completed
