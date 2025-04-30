<H3>Naveen Kanthan L</H3>
<H3>212223230138</H3>
<H3>EX. NO.1</H3>
<H3>30 - 4 - 2025</H3>
<H1 ALIGN =CENTER> Introduction to Kaggle and Data preprocessing</H1>

## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

**Kaggle :**
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

**Data Preprocessing:**

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

**Need of Data Preprocessing :**

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
STEP 1:Importing the libraries<BR>
STEP 2:Importing the dataset<BR>
STEP 3:Taking care of missing data<BR>
STEP 4:Encoding categorical data<BR>
STEP 5:Normalizing the data<BR>
STEP 6:Splitting the data into test and train<BR>

##  PROGRAM:
```
#import libraries
from google.colab import files
import pandas as pd
import io
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split

#Opening the file
df = pd.read_csv("Churn_Modelling.csv")
df.head()
df.tail()
df.info()
df.columns

# Finding Missing Values
df.isnull().sum()

#Check for Duplicates
df["duplicated"] = df.duplicated()

df.loc[df["duplicated"] == True]

#Detect Outliers
import matplotlib.pyplot as plt
data = ["CreditScore", "NumOfProducts", "Balance", "Tenure", "Age"]
fig, axes =  plt.subplots(1, 5, figsize =(15,5))

for i, col in enumerate(data):
  axes[i].boxplot(df[col])
  axes[i].set_title(f"{col}")

plt.tight_layout()
plt.show()

#Normalize the dataset
standard = StandardScaler()

cols = ['Surname','Geography','Gender','duplicated']
df_copy = df.drop(columns = cols)
df_copy = pd.DataFrame(standard.fit_transform(df_copy_1), columns=df_copy_1.columns)
df_copy.head()

#split the dataset into input and output
input_df = df_copy.drop('Exited', axis = 1)
input_df.head()

output_df = df_copy['Exited']
output_df

#splitting the data for training & Testing
x_train, x_test, y_train, y_test = train_test_split(input_df, output_df, test_size = 0.3, random_state =434)

#Print the training data and testing data
x_train
y_train
x_test
y_test
```


## OUTPUT:
### df.head()
![ss1](https://github.com/user-attachments/assets/2f23ae94-4b3e-4207-a0a3-9874546e7f36)

### df.tail()
![ss2](https://github.com/user-attachments/assets/ea7093ba-bd30-45d4-bd99-7f5e95a306c1)

### Missing values
![ss3](https://github.com/user-attachments/assets/5aefdd8e-157b-4b67-ab2a-df4b96cc4fa3)

### Outliers
![ss5](https://github.com/user-attachments/assets/c8f8966b-69ed-481e-ba24-d39e5739c8f2)

### Normalizing
![ss6](https://github.com/user-attachments/assets/9518e64c-4c17-4361-acf1-1eff3ad2a349)

### Input and Output
![ss7](https://github.com/user-attachments/assets/0ec566e5-16ad-4bff-8ead-54d5f4b772bb)
![ss8](https://github.com/user-attachments/assets/5ae710e3-6099-4172-a753-fa1249b4b44d)

### Testing Values (x_test and y_test)
![ss9](https://github.com/user-attachments/assets/9e11257a-848f-4ac7-a06f-3abd4caadcb2)
![ss10](https://github.com/user-attachments/assets/31f1584d-8e26-4595-8ca5-625362ede85f)


## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.


