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
df=sns.load_dataset("tips")
df
```

<img width="570" height="520" alt="image" src="https://github.com/user-attachments/assets/91c50024-f41c-41b8-84a9-f8383db1c1b8" />

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto",palette="Set1")
```

<img width="980" height="593" alt="image" src="https://github.com/user-attachments/assets/761ae32a-291f-4e5b-81f4-a741a72d3ad6" />

```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel('Y Label')
```
<img width="750" height="762" alt="image" src="https://github.com/user-attachments/assets/c1323487-8f5f-49a1-afd8-b181dcd95b48" />
```
tips=sns.load_dataset("tips")
avg_total_bill=tips.groupby("day")["total_bill"].mean()
avg_tip=tips.groupby("day")["tip"].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip")
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average total bill and tip by day")
plt.legend()
plt.show()
```

<img width="926" height="742" alt="image" src="https://github.com/user-attachments/assets/d809c0c0-aea7-4e70-9415-831709c19a6d" />

```
avg_total_bill=tips.groupby("time")["total_bill"].mean()
avg_tip=tips.groupby("time")["tip"].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip",width=0.4)
plt.xlabel("Time of the day")
plt.ylabel("Amount")
plt.title("Average total bill and tip by Time of the Day")
plt.legend()
```
<img width="839" height="570" alt="image" src="https://github.com/user-attachments/assets/b965a21a-1f1c-4471-bbca-d8cfba0e4483" />
```
import seaborn as sns
df=sns.load_dataset("tips")
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette='Set3')
plt.xlabel("Day of the week")
plt.ylabel("Total bill")
plt.title("total bill by day and gender")
```

<img width="886" height="699" alt="image" src="https://github.com/user-attachments/assets/e9165f02-ace3-4526-89b5-9c87badd19a4" />

```
import seaborn as sns
df=sns.load_dataset("tips")
sns.scatterplot(x="total_bill",y="tip",hue="sex",data=df,palette='Set1')
plt.xlabel("Total bill")
plt.ylabel("Tip")
plt.title("Scatter plot of total bill vs tip amount")
```

<img width="860" height="706" alt="image" src="https://github.com/user-attachments/assets/22136a99-6dc4-4712-874a-d79707cedcf4" />

```
sns.histplot(x="total_bill",hue="smoker",data=df,kde=True,palette='Set1')
plt.xlabel("Total bill")
plt.ylabel("Frequency")
plt.title("Distribution of total bill by gender")
```

<img width="837" height="657" alt="image" src="https://github.com/user-attachments/assets/d955087f-f981-4094-9948-f6e33f5d5810" />

```
import seaborn as sns
import pandas as 
df=sns.load_dataset('tips')
sns.boxplot(x='day',y='total_bill',hue="sex",data=df,palette='Set2')
```

<img width="859" height="643" alt="image" src="https://github.com/user-attachments/assets/d349bfef-7ee8-4272-817c-83f6c8e67fcd" />

```
sns.boxplot(x='day',y='total_bill',hue="smoker",data=df,linewidth=2,width=0.6,fliersize=7,flierprops={"marker":"o","markerfacecolor":"grey"},boxprops={"facecolor":"red","edgecolor":"black"},whiskerprops={"color":"darkblue","linestyle":"--","linewidth":"-","linewidth":"2"},palette='Set1')

```

<img width="859" height="609" alt="image" src="https://github.com/user-attachments/assets/462cad4b-c592-4975-a5a8-54828ddf00ab" />

```
sns.violinplot(x='day',y='total_bill',hue="smoker",data=tips,linewidth=2,width=0.6,palette='Set1',inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total bill")
plt.title("Violin plot of total bill by day and smoker status")
```

<img width="941" height="691" alt="image" src="https://github.com/user-attachments/assets/07fe50d7-6033-46a2-92d1-6622958cf8aa" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip,palette='Set2')

```

<img width="828" height="644" alt="image" src="https://github.com/user-attachments/assets/76392f9e-405a-4203-9678-f959e081ea40" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"],palette='Set1')
```

<img width="979" height="636" alt="image" src="https://github.com/user-attachments/assets/9d8d0677-87ca-4788-9971-e71aaed85679" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip=sns.load_dataset('tips')
sns.violinplot(x='tip',y='day',data=tip,palette='rainbow')
```

<img width="825" height="630" alt="image" src="https://github.com/user-attachments/assets/8f7bdfde-cc7c-4b83-9e3b-3af53f759ac9" />

```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="layer",linewidth=3,palette='Set2',alpha=0.8)

```

<img width="1024" height="582" alt="image" src="https://github.com/user-attachments/assets/5d6b3c56-3328-4143-8f90-8d72852f5159" />

```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="stack",linewidth=3,palette='Set3',alpha=0.8)
```

<img width="1031" height="589" alt="image" src="https://github.com/user-attachments/assets/2903447c-188a-4cc1-8768-377a68f0042f" />

```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="fill",linewidth=3,palette='Set1',alpha=0.8)

```

<img width="1007" height="590" alt="image" src="https://github.com/user-attachments/assets/2c61ec5c-6653-4642-9b06-3c0b22c1c798" />

```
import seaborn as sns
tip=sns.load_dataset('tips')
num=tips.select_dtypes(include=['float64','int64']).columns
corr=tips[num].corr()
sns.heatmap(corr,annot=True,cmap="YlGnBu")

```

<img width="779" height="560" alt="image" src="https://github.com/user-attachments/assets/23c149c9-503a-44ed-9f58-0e736ef8223f" />

```
sns.heatmap(corr,cmap="YlGnBu")

```

<img width="798" height="563" alt="image" src="https://github.com/user-attachments/assets/63e58eb3-fd03-48b5-b6d9-6f7e41e633b4" />


# Result:
Thus the given Data Visualization using Seaborn library is executed successfully.
