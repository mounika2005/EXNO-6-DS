# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/48269e1b-c9eb-4b9a-bfa4-9718067cc094)

```
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/1fc40de5-2340-4601-a84f-591e55109026)
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![image](https://github.com/user-attachments/assets/8e473cf1-b390-4ffb-b7ed-b62c665cfcef)
```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
```

```
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![image](https://github.com/user-attachments/assets/9488b382-cd3d-4c24-854e-063743848f9f)
```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/9266e423-b149-495b-b430-f626c1789892)
```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/78ea969c-c154-4fe0-a1db-92eef5bbb46d)
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/0af96081-7da9-44cf-adf1-4ff12fc29201)
```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/2078a978-135b-40ab-9993-87737e3d1d74)
```
tit= pd.read_csv('/content/titanic_dataset.csv')
tit
```
![image](https://github.com/user-attachments/assets/5a20ff8c-33bf-4c7f-815b-8bc9782c48c8)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/6ce01748-9832-4de5-9e53-35707fa08abe)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/ae669f28-aaa0-48cf-9fc4-654590acd4f5)
```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/024fa79c-fb6d-46b4-aefe-57cacf7b741a)
```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/c3ffecbf-ceb8-4bc9-b761-83af15a660bc)
```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/20569024-e599-4726-8361-5fa0506b531c)
```
df=pd.read_csv('/content/titanic_dataset.csv')
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![image](https://github.com/user-attachments/assets/0c7bf0fe-fc37-47df-84a0-e8245729ed07)
```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/ebfdc7a9-ee50-4921-9b57-b7b819e23bd8)
```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/f65ffe95-8d33-4d89-8185-7da9594d6f52)
```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/92b81054-8deb-4aa3-8ceb-863cb10ea9fc)
```
mart=pd.read_csv('/content/titanic_dataset.csv')
mart
```
![image](https://github.com/user-attachments/assets/0471cb6f-445d-477d-925d-c4e46aae5d18)
```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```

![image](https://github.com/user-attachments/assets/29e2e430-1325-4c03-bf03-8811ace00686)
```
sns.kdeplot(data=mart,x='PassengerId')
```
![image](https://github.com/user-attachments/assets/f5619ae8-cd88-4a05-bdb1-1b4fcda36eaa)
```
sns.kdeplot(data=mart,x='Age')
```
![image](https://github.com/user-attachments/assets/c0dd3abb-06e4-4e20-a5ef-b0081442a63e)
```
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/c39404ca-78c6-46c8-a0f9-4bb4cdb3769e)
```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/01fb46e4-f9b8-476f-b73a-3d22691bd77f)
```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/431d436c-0687-4ddf-94a4-c403c29f6c74)
```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/d2563a90-4fdc-4195-b772-c6e6eef23018)
```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/08917d7d-1a74-4c8b-b845-0b4eda03635f)




# Result:
          Thus Data Visualization using seaborn python library for the given data is done successfully.
 
