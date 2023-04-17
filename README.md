# DS-EXERCISE-4    
                             
# MULTIVARIATE ANALYSIS

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

## RESULT

Thus the program to perform EDA on the given data set is successfully executed.

