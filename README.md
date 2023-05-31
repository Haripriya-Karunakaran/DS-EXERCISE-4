# EXERCISE-4           MULTIVARIATE ANALYSIS

## Aim: 

To Perform Multivariate analysis on the given data sets. 

## Algorithm: 

STEP 1: Import the built libraries required to perform EDA and outlier removal.  
 
STEP 2: Read the given csv file  
 
STEP 3: Convert the file into a dataframe and get information of the data.  
 
STEP 4: Return the objects containing counts of unique values using (value_counts()).  
 
STEP 5: Plot the counts in the form of Histogram or Bar Graph.  
 
STEP 6: Use seaborn the bar graph comparison of data can be viewed.  
 
STEP 7: Find the pairwise correlation of all columns in the dataframe.corr()  
 
STEP 8: Save the final data set into the file 

## CODE:

## SUPERSTORE.CSV

import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = pd.read_csv("/content/SuperStore.csv")

df.head(10)

df.isnull().sum()

df.info()

df.dtypes

df.describe()

sns.scatterplot(x = df['Postal Code'],y = df['Sales'])

states=df.loc[:,["State","Sales"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("SALES")

plt.show()

states=df.loc[:,["State","Postal Code"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Postal Code",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("Postal Code")

plt.show()

states=df.loc[:,["Segment","Sales"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("SEGMENT")

plt.ylabel=("SALES")

plt.show()

sns.barplot(x = df['Postal Code'],y = df['Ship Mode'],hue=df['Region'])

df.corr()

sns.heatmap(df.corr(),annot=True)

## OUTPUT:

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/cfbd9096-3bff-4fb5-8fa6-a6f39986ae9f)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/92bcea49-403b-4114-83db-6f96aaa77020)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/cf50eb9b-affc-4958-9d6e-a39670506c51)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/549f9300-49bc-4b81-82b6-328d3f43d7e8)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/6cf6ef28-91a0-4bd9-b94b-f5397bb8e6f6)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/f6ec80cb-6770-476b-b9a3-c15f80c310de)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/fc0e131b-d660-4baf-a671-6585d48c4983)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/316267bb-8b3d-43fe-a4a6-0344392847d5)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/37240631-7225-4364-aa01-e74aa2d0fe67)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/79b8627f-3e2a-4476-9b14-07a11a6fed98)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/03ff230f-0c5e-481d-88c5-eac12d706267)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/4e0a5fce-ba60-429b-a5f9-925c54879d02)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-4/assets/126390051/c5b843e6-0552-423c-ab1b-c0a01e7631cc)

## RESULT

Thus the program to perform EDA on the given data set is successfully executed.

