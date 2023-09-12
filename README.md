# Ex-04-Multivariate-Analysis

## AIM :
To perform Multivariate EDA on the given data set.

## EXPLANATION :
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM :
## STEP 1:
Import the built libraries required to perform EDA and outlier removal.

## STEP 2:
Read the given csv file.

## STEP 3:
Convert the file into a dataframe and get information of the data.

## STEP 4:
Return the objects containing counts of unique values using (value_counts()).

## STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr() .

## STEP 8:
Save the final data set into the file.

## PROGRAM
```
R.JOYCE BEULAH
212222230058
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns


dt = pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/3fe89917-991d-4ed8-8457-222fca43ea64)

```
dt.set_index("PassengerId",inplace=True)

dt.describe()
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/51ec43dc-65b7-422e-a784-873fde7a875b)

```
dt.info()
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/a1521f40-a4ab-460a-90a4-74ae12c0072f)

```
dt.shape
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/86dd7102-9c3e-4ee6-8508-71122b0b657e)

```
dt.nunique()
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/d043b789-7c95-4d8c-86f7-5a2d27a4655b)

```
dt["Survived"].value_counts()
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/7c9ad825-25e8-49e8-8bc1-5dc7a0bf1cad)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/d74be789-824f-4ecf-83f0-13c6ddfb630c)

```
sns.catplot(x="Age",col="Survived",kind="count",data=dt)
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/5e0452ce-9476-4265-8a66-8c047e11bcb9)

```
fig,ax1=plt.subplots(figsize=(8,5))
graph = sns.countplot (ax=ax1,data=dt,x="Survived",hue="Pclass",palette="rainbow")
graph.set_xticklabels(graph.get_xticklabels())
for p in graph.patches:
  height = p.get_height()
  graph.text(p.get_x()+p.get_width()/2,height+20.8,height ,ha="left")
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/c65821ff-9d2b-4765-9671-d66b6b6c7d14)

```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/52478db6-6a38-4cb3-9f04-3af5e510890e)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/eaa8e177-1257-4548-b75c-d69eb45998cc)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/0c3d7912-98d7-4cee-8088-330466f1adea)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Parch',data=dt)
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/fcf8bcb1-6e13-44d5-9c43-2009ea49973f)

```
sns.catplot(data=dt,col="Survived",x="Parch",hue='Pclass',kind="count")
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/1a4ffcee-77c4-492b-893b-277cffac4513)

```
g=sns.catplot(data=dt,col="Survived",x="Parch",hue="Pclass",kind ="count",legend=True)
g.fig.set_size_inches(8,5)
g.fig.subplots_adjust(top=0.81,right=0.86)
ax=g.facet_axis(0,0)
for p in ax.patches:
  ax.text(p.get_x()-0.01,p.get_height()*1.02,'{0:.1f}'.
  format(p.get_height()),color='red',rotation="horizontal",size="small")
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/d82aafa8-a7a4-4509-bfd5-f965e781f534)

```
corr = dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/9affed0c-cba7-427e-a74f-15441e3b9a2f)

```
sns.pairplot(dt)
```
![image](https://github.com/JoyceBeulah/Ex-04-Multivariate-Analysis/assets/118343698/c574f22b-29c3-48ac-8b49-a98923763cfe)


## RESULT:
Thus the program to perform Multivariate EDA on the given data set is successfully executed.
