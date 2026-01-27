<H3>ENTER YOUR NAME</H3>
<H3>ENTER YOUR REGISTER NO.</H3>
<H3>EX. NO.1</H3>
<H3>DATE</H3>
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
TYPE YOUR CODE HERE
import pandas as pd
import io
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split

data = pd.read_csv("Churn_Modelling.csv")
print(data.head())
print(data.tail())

X=data.iloc[:,:-1].values
print(X)

y=data.iloc[:,-1].values
print(y)

data.info()

print("Missing Values: \n ",data.isnull().sum())

print("Duplicate values:\n ")
print(data.duplicated())

data.describe()

data = data.drop(['Surname', 'Geography','Gender'], axis=1)
data.head()

scaler=MinMaxScaler()
df1=pd.DataFrame(scaler.fit_transform(data))
print("Normalized data \n" , df1)

X = data.drop('Exited', axis=1)  
y = data['Exited'] 

X_train ,X_test ,y_train,y_test=train_test_split(X,y,test_size=0.2,random_state=42)
print("Training data")
print(X_train)
print(y_train)

print("Testing data")
print(X_test)
print(y_test)
print("Length of X_test: ", len(X_test))

## OUTPUT:
SHOW YOUR OUTPUT HERE
df.head()
<img width="784" height="704" alt="Screenshot 2026-01-27 161224" src="https://github.com/user-attachments/assets/f8f43061-e8b8-4a90-b7dc-d061ec3adb95" />

df.tail()
<img width="653" height="345" alt="Screenshot 2026-01-27 162216" src="https://github.com/user-attachments/assets/18ce23da-18b0-4b14-af8e-c2aa8a958b55" />

X & Y Values
<img width="472" height="151" alt="Screenshot 2026-01-27 162519" src="https://github.com/user-attachments/assets/6bf4d678-0498-49e6-9343-6f7a0d34bb69" />

Data.info()
<img width="425" height="370" alt="Screenshot 2026-01-27 162639" src="https://github.com/user-attachments/assets/623c4440-1f9b-4d88-a83f-06e119d9ff54" />

Missing Values
<img width="337" height="287" alt="Screenshot 2026-01-27 162703" src="https://github.com/user-attachments/assets/2f96c53c-be68-436a-b0a9-5bd24cacbe33" />

Duplicate Value
<img width="1353" height="547" alt="Screenshot 2026-01-27 162759" src="https://github.com/user-attachments/assets/9d8332e9-c787-4c18-bb6f-a3fcf88d948a" />

Normalized data 
<img width="682" height="485" alt="Screenshot 2026-01-27 162856" src="https://github.com/user-attachments/assets/b579210f-bf5e-438a-b276-85092f80301e" />













## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.


