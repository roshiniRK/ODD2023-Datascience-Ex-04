# Ex:04 Multivariate Analysis :
## AIM :
To perform Multivariate EDA on the given data set.
## EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset.
This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning. The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM
### STEP 1 :

Import the built libraries required to perform EDA and outlier removal.
### STEP 2 :

Read the given csv file
### STEP 3 :

Convert the file into a dataframe and get information of the data.
### STEP 4 :

Return the objects containing counts of unique values using (value_counts()).
### STEP 5 :

Plot the counts in the form of Histogram or Bar Graph.
### STEP 6 :

Use seaborn the bar graph comparison of data can be viewed.
### STEP 7 :

Find the pairwise correlation of all columns in the dataframe.corr()
### STEP 8 :
Save the final data set into the file

## PROGRAM :
### NAME : ROSHINI R K
### REG NO : 212222230123

 DIABETES.CSV :
```
import pandas as pd
import numpy as np
import seaborn as sb
from scipy import stats
import matplotlib.pyplot as plt
df = pd.read_csv("diabetes.csv")

df.info()

df.isnull().sum()

sb.boxplot(data=df)

# DATA CLEANING
z = np.abs(stats.zscore(df['Glucose']))
dfc=df[(z<2)]
z = np.abs(stats.zscore(dfc['BloodPressure']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['SkinThickness']))
dfc=dfc[(z<3)]
z = np.abs(stats.zscore(dfc['BMI']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Insulin']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['DiabetesPedigreeFunction']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Age']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Outcome']))
dfc=dfc[(z<3)]

sb.boxplot(data=dfc)
plt.figure(figsize = (14,6))
sb.scatterplot(x ='Glucose',y='BloodPressure',data = df)

sb.scatterplot(x = 'Glucose',y='Insulin',data = df)

sb.scatterplot(x = 'Glucose',y='DiabetesPedigreeFunction',data = df)

sb.scatterplot(x = 'Glucose',y='Age',data = df)

sb.heatmap(df.corr(),annot = True)

```

## OUTPUT :



![Screenshot 2023-10-10 210437](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/31d6ea42-4563-41c3-8285-4d6512c9a892)

![Screenshot 2023-10-10 210443](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/eca19166-df57-4f65-9da5-159b4897257d)

![Screenshot 2023-10-10 210450](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/08e2349d-a92d-4b2d-93ec-3e947288d458)


![Screenshot 2023-10-10 210458](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/20e9a9f8-96af-493d-9bda-9b6530547778)


![Screenshot 2023-10-10 210518](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/36280f3a-493d-426d-85d5-b50b20c3ed85)

![Screenshot 2023-10-10 210526](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/a6c0fdf6-f075-4cdf-a545-e6005663a148)

![Screenshot 2023-10-10 210534](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/5a23962a-9e53-4638-abbd-ba74638ce1e5)

![Screenshot 2023-10-10 210541](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/c1729fc5-9455-42d2-bead-42e1850c40c2)

### HEAT MAP :

![Screenshot 2023-10-10 210604](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/86faf5b8-2443-4d91-9767-542dd3b39b98)

## PROGRAM :
### SUPERSTORE.CSV :
```
import pandas as pd
import numpy as np
import seaborn as sb
from scipy import stats
import matplotlib.pyplot as plt
df = pd.read_csv("SuperStore.csv")

df.info()

df.isnull().sum()

# FILLING NULL VALUES
df['Postal Code'] = df['Postal Code'].fillna(value=df['Postal Code'].mode()[0])
df.isnull().sum()
sb.boxplot(data=df)

# DATA CLEANING
z = np.abs(stats.zscore(df['Sales']))
df = df[z<3]

sb.boxplot(data=df['Sales'])

sb.scatterplot(x = 'Postal Code',y='Sales',data = df)

sb.scatterplot(x = 'Row ID',y='Sales',data = df)

sb.heatmap(df.corr(),annot = True)

```
## OUTPUT :

![Screenshot 2023-10-10 211921](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/06d13106-6854-42ff-b9f1-9723d1a7e77b)

![Screenshot 2023-10-10 211929](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/8d5602b2-9512-4c94-9d26-8b290c3be418)

![Screenshot 2023-10-10 211937](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/b86e71fc-9a7f-4622-8731-f165cf117e89)

![Screenshot 2023-10-10 211945](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/9862e9e2-1883-44ce-aaee-6175612a058d)
![Screenshot 2023-10-10 211952](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/57d96036-228b-43da-ae49-29f7802c4928)

![Screenshot 2023-10-10 211958](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/28ce8eb3-de4a-4b99-8055-f47269422458)
### HEAT MAP :

![Screenshot 2023-10-10 212007](https://github.com/Mamthaiyappaprabu/ODD2023-Datascience-Ex-04/assets/119393563/2aaffd9d-bfcf-46c2-84d4-448a73e1609d)

## RESULT :
Thus we have read the given data and performed the multivariate analysis with different types of plots.
