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
![6 1](https://github.com/user-attachments/assets/f82f05d0-1d8f-45aa-a442-a7ca9b83c03f)

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto",palette="Set1")
```
![6 2](https://github.com/user-attachments/assets/4b78f56a-b5f9-44ea-b33f-b4c490769bbc)

```
tips=sns.load_dataset("tips")
avg_total_bill=tips.groupby("day")["total_bill"].mean()
avg_tip=tips.groupby("day")["tip"].mean()
```
![6 3](https://github.com/user-attachments/assets/4cf6781d-720f-47f8-a382-2d76a4b31b2c)

```
plt.figure(figsize=(8,6))
plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill")
plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip")
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()
```
![6 4](https://github.com/user-attachments/assets/ae0515a8-043a-4282-9e57-5c42dc1c5997)

```
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()
```
![6 5](https://github.com/user-attachments/assets/b068b60f-8f71-4037-8d1f-2e0b241ee184)

```
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip",width=0.4)
plt.xlabel("Time of Day")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Time of Day")
plt.legend()
plt.show()
```
![6 6](https://github.com/user-attachments/assets/30b07340-313c-474e-a39f-b37600b3fa2f)

```
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette="Set3")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Sex")
plt.show()
```
![6 7](https://github.com/user-attachments/assets/b7e7cc35-534a-48d9-b9da-dd5338b1c7b0)

```
df=sns.load_dataset("tips")
sns.scatterplot(x="total_bill",y="tip",hue="sex",data=df,palette="Set1")
plt.xlabel("Total Bill")
plt.ylabel("Tip")
plt.title("Total Bill vs. Tip by Sex")
plt.show()
```
![6 8](https://github.com/user-attachments/assets/d46f3513-8d26-4a47-be56-f406c31f7a23)

```
sns.histplot(data=df,x="total_bill",hue="smoker",kde=True,palette="Set1",color="red")
plt.xlabel("Total Bill")
plt.ylabel("Frequency")
plt.title("Distribution of Total Bill")
```
![6 9](https://github.com/user-attachments/assets/6bed6ecd-c5b1-49e2-af1d-644365c9ffdd)

```
df=sns.load_dataset("tips")
sns.boxplot(x="day",y="total_bill",hue="sex",data=df,palette="Set2")
```
![6 10](https://github.com/user-attachments/assets/a3fdc278-0d8e-41d2-bd72-353c02373190)

```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=df,linewidth=2,width=0.6,
            fliersize=7,flierprops={"marker":"o","markerfacecolor":"grey"},
            boxprops={"facecolor":"red","edgecolor":"black"},
            whiskerprops={"color":"darkblue","linestyle":"--","linewidth":2},
            capprops={"color":"darkblue","linestyle":"--","linewidth":2},palette="Set1")
```
![6 11](https://github.com/user-attachments/assets/94a23852-53fc-4863-9568-a32de2b06f45)

```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette="Set1",inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Distribution of Total Bill by Day and Smoker Status")
```
![6 12](https://github.com/user-attachments/assets/2339b4fa-a3d9-4d08-9a5c-b5b1d0082274)

```
sns.set(style="whitegrid")
tip=sns.load_dataset("tips")
sns.violinplot(x="day",y="tip",data=tip,palette="Set2")
```
![6 13](https://github.com/user-attachments/assets/964c505c-3ee4-4434-a22e-4bdce29761db)


```
import seaborn as sns
sns.set(style="whitegrid")
tips=sns.load_dataset("tips")
sns.violinplot(x=tip["total_bill"],palette="Set1")
```
![6 14](https://github.com/user-attachments/assets/327b419a-d99e-43e3-be02-2bcef940b9a9)

```
sns.set(style="whitegrid")
tips=sns.load_dataset("tips")
sns.violinplot(x="tip",y="day",data=tip,palette="rainbow")
```
![6 15](https://github.com/user-attachments/assets/a35e2180-66b4-49c1-96d4-f698d2ba7507)

```
sns.kdeplot(data=tips,x='total_bill',hue="time",multiple="layer",linewidth=3,palette="Set2",alpha=0.8)
```
![6 16](https://github.com/user-attachments/assets/74b8e92c-5502-4ac1-8d5e-b1f2ba5c4713)

```
sns.kdeplot(data=tips,x='total_bill',hue="time",multiple="stack",linewidth=3,palette="Set3",alpha=0.8)
```
![6 17](https://github.com/user-attachments/assets/7d2a4efd-55e4-4c21-828e-4043165b1696)

```
sns.kdeplot(data=tips,x='total_bill',hue="time",multiple="fill",linewidth=3,palette="Set1",alpha=0.8)
```

```![6 18](https://github.com/user-attachments/assets/d2e757ac-901f-469c-b00f-071c9e34aaec)

tips=sns.load_dataset("tips")
num=tips.select_dtypes(include=['float64','int64']).columns
corr=tips[num].corr()
sns.heatmap(corr,annot=True,cmap="YlGnBu")
```
![6 19](https://github.com/user-attachments/assets/27500094-f77d-4ac0-a50e-5efc7adf9f4c)

```
sns.heatmap(corr,cmap="YlGnBu")
```
![6 20](https://github.com/user-attachments/assets/00e3baae-baad-4361-81e7-81c049cdda89)


# Result:

Thus the data visualization techniques of seaborn has been implemented.
