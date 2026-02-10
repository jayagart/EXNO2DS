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


```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd. read_csv ( "/content/titanic_dataset.csv" )
dt
```

<img width="775" height="272" alt="image" src="https://github.com/user-attachments/assets/f1d1dbf1-c093-4e57-9fcb-19fba560343a" />

```
dt.info()
```

<img width="114" height="44" alt="image" src="https://github.com/user-attachments/assets/376834d6-e58a-4d9f-8301-613329dadfe1" />

```
dt.shape
```
<img width="230" height="220" alt="image" src="https://github.com/user-attachments/assets/9f175e67-8a51-4a37-ace6-66fb5f9aa2b2" />


```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```

<img width="714" height="347" alt="image" src="https://github.com/user-attachments/assets/ece7fb06-7d53-47b9-adb3-0fe3d3ba2868" />

```
dt.nunique()
```

<img width="180" height="488" alt="image" src="https://github.com/user-attachments/assets/e10ae2ed-a970-437e-98a3-0af7f7660a8f" />

```
dt ["Survived"].value_counts()
```

<img width="179" height="201" alt="image" src="https://github.com/user-attachments/assets/9f3f668a-a150-4755-9f5c-62281c1ff095" />


```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per

```

<img width="166" height="208" alt="image" src="https://github.com/user-attachments/assets/e5945c56-2dc1-4c2f-9ecb-492eea3cedc6" />


```
sns.countplot(data=dt,x="Survived")
```

<img width="722" height="550" alt="image" src="https://github.com/user-attachments/assets/205d614a-1971-46be-83ed-cffc3c80b80e" />

```
dt
```

<img width="777" height="305" alt="image" src="https://github.com/user-attachments/assets/891c53ae-a8fd-4129-8bb1-ab6fa69e408d" />


```
dt.Pclass.unique()
```
<img width="97" height="28" alt="image" src="https://github.com/user-attachments/assets/ad762af7-36db-4950-97af-d2851e175cb1" />

```
dt.rename(columns={'Sex':'Gender'}, inplace=True)
dt
```
<img width="836" height="323" alt="image" src="https://github.com/user-attachments/assets/2a57173c-2c6c-4961-a3aa-f7a8018658f6" />

```
sns.catplot(x="Gender", col="Survived", kind="count",data=dt, height=5, aspect =.7)
```
<img width="770" height="562" alt="image" src="https://github.com/user-attachments/assets/ae2ae7d1-c06d-4770-9bde-e3be3e271f41" />


```
sns.catplot(x='Survived',hue="Gender", data=dt, kind='count')
```

<img width="653" height="560" alt="image" src="https://github.com/user-attachments/assets/1f7bb160-ae06-4d0a-92b0-c92ebdf35e07" />

```
dt.boxplot(column="Age",by="Survived")
```

<img width="619" height="520" alt="image" src="https://github.com/user-attachments/assets/00b0e6a9-7a82-41b4-88cd-83cf47eaccdd" />

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

<img width="651" height="492" alt="image" src="https://github.com/user-attachments/assets/5d832fc1-f7af-442a-afc7-608b2cce8740" />

```
sns.jointplot(x="Age",y="Fare",data=dt)
```

<img width="664" height="665" alt="image" src="https://github.com/user-attachments/assets/8b2aa2ed-0411-47d9-aa53-56ca61a19de1" />

```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```

<img width="758" height="521" alt="image" src="https://github.com/user-attachments/assets/f13ac1a9-8c8f-487e-8e88-30f2aa9e6d6b" />

```
sns.catplot(data=dt, col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="865" height="413" alt="image" src="https://github.com/user-attachments/assets/119418fe-0a71-49cb-9e8c-a7f4b1629f56" />

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

dt = pd.read_csv("titanic_dataset.csv")
dt_numeric = dt.select_dtypes(include='number')
corr = dt_numeric.corr()
plt.figure(figsize=(10,6))
sns.heatmap(corr, annot=True, cmap='coolwarm')
plt.show()
```

<img width="691" height="440" alt="image" src="https://github.com/user-attachments/assets/7ba3a192-8c89-47d7-9d38-5d0449aa4267" />

```
sns.pairplot(dt)
```

<img width="1211" height="815" alt="image" src="https://github.com/user-attachments/assets/7294b8ed-3183-4804-a1de-9f7c4d480ccd" />

# RESULT
        Thus, the Exploratory Data Analysis on the given data set was performed successfully
