# CUSTOMER_SEGMENTATION_PROJECT 
---

This project is about subcription service which involves dividing subscribers into distinct groups based on factors such as usage patterns, engagement levels, demographics, and preferences. My aim is to analyse Customer Data for different Subscription services, and to identify different segments and trends.

## PROJECT TITLE: Customer Segmentation for Subscription Service 
---

[Project Overview](#Project_Overview)

[Data Analysis Sources](#Data_Analysis_Sources)

[Tools Used](#Tools_Used)

[Data Cleaning and Preparation](#Data_Cleaning_and_Preparation)

[Data Analysis](#Data_Analysis)

[Data Visualization](#Data_Visualization)

## Project Overview 
---

The goal of this project is to analyse the strategy for a subscription-based service and  to optimize marketing efforts, improve customer retention, and enhance the overall user experience. By analyzing subscriber data, I aim to identify distinct customer groups based on their behavior, preferences, and demographics, allowing for more targeted and effective engagement strategies.

## Data Analysis Sources 
---

The primary source of this data is gotten from an online tutorials such as Linkedin, Youtube and oter CSV files. 

## Tools Used 
--- 

- Microsoft Excel [Download Here](https://www.microsoft.com)
   1. For Data Cleaning
   2. For Calculations using Excel Formulas
   3. For creating Summarization using Pivot Tables
   4. For Data Visualization.

 - SQL-Structured Query Language [Downlaod Here](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)

    It is used for Data Query such as;
    Finding the most Popular Subscription Type by the number of Custommers, Calculating Total Revenue by Subacription Type, Finding the Top 3 Regions by Subscription 
Cancellations.

 - Power BI Desktop [Download Here](https://powerbi.microsoft.com/desktop/)

    It is used to Create a Dashboard that Visualizes the insights found in both EXCEL, SQL and BI Reports.

 - GitHub [Download Here](https://github.com)

    It is used for Porfolio Building.

## Data Cleaning and Preparation 
---

Data cleaning and preparation are critical steps in ensuring that the data used for customer segmentation is accurate, complete, and ready for analysis. 
    1. Data Collection and Data Cleaning 
    2. Data Transformation and Data Splitting. 

## Data Analysis 
---

Once the data is cleaned and prepared, the next step is to conduct a thorough data analysis to identify patterns and insights that can drive the customer segmentation process. The goal of this phase is to explore customer behaviors, preferences, and attributes. Here are some key steps involving in data analysis process for customer segmentation.
1. Descriptive Statistics: Calculate and analyze key summary statistics for each variable, such as:

     - Region by Total Revenue

![Pie Chart 2 1](https://github.com/user-attachments/assets/edd8e0d6-9bf0-49c5-bf8c-6926cd843a0f)

     
     
     - Subscription Type by CustomerID 

     
![Pie Chart 2 2](https://github.com/user-attachments/assets/0c6addd0-b082-4c8f-a257-e9c178f16222)

     
     - Subscription Type by Revenue 


![Bar Chart 2 1](https://github.com/user-attachments/assets/0620db62-d370-4cf3-a19a-05e4fb07a532)

     - Subscription Type by SUB Duration



![Pie chart 2 3](https://github.com/user-attachments/assets/dc37b965-0154-4995-affa-f1418b1db6f7)

     - Region by CustomerID


![Bar chart 2 3](https://github.com/user-attachments/assets/a662538f-bf8f-43d9-a5d6-791848840fb2)

     
     - Region by SUB Duration 


![Pie chart 2 4](https://github.com/user-attachments/assets/1dae2592-6c27-4da1-a41d-6070cca12a2a)

     - Region by Revenue 


![Bar chart 2 2](https://github.com/user-attachments/assets/549cd6fc-cc79-48fe-a748-ba24467e5e50)   


---




2. Customer Performance: In this context, understanding how each customer or customer segment contributes to the service’s growth, revenue, and sustainability in;
    - finding the most popular Subscription Type by the number of Customers.

      ```SQL
      Select * from CustomerSEG 


![Cus 1](https://github.com/user-attachments/assets/07dfc950-a6e5-4bbf-8225-3a075e3fbbb9) 


       ```SQL
       Select Region, count(CustomerID) as Total_customers from CustomerSEG 
       Group by Region  



![Cus 2](https://github.com/user-attachments/assets/cb47f079-b53c-4b14-b0e7-8080432040e2)



       ```SQL
       Select SubscriptionType, count(CustomerID) as Total_customers from CustomerSEG 
       Group by SubscriptionType
       Order by Total_customers DESC 


![Cus 3](https://github.com/user-attachments/assets/bc8ffbfe-abe3-4215-a9b7-5ef978ebb41a) 



      ```SQL 
      Select CustomerID, Subscriptionstart, subscriptionend from CustomerSEG
      Where datediff(month,subscriptionstart,subscriptionend) <=6 


      

![Cus 5](https://github.com/user-attachments/assets/c685131c-b54e-4211-be68-481ceed3fc7a) 



     ```SQL 
     Select AVG(datediff(month, Subscriptionstart,subscriptionend)) as average_duration 
     From CustomerSEG 



![Cus 6](https://github.com/user-attachments/assets/f1626238-6875-4486-875f-f027f8beba17) 



     ```SQL
     Select CustomerID
     From CustomerSEG
     Where datediff(month, subscriptionstart, subscriptionend)  >12 



![Cus 7](https://github.com/user-attachments/assets/9dcc8151-a742-45c7-855b-53ba3eb70c8f)  



    ```SQL 
    Select subscriptionType, Sum(Revenue) as Total_Revenue from CustomerSEG
    Group by SubscriptionType 



![Cus 8](https://github.com/user-attachments/assets/3ef5f9d1-8094-42e1-9d58-d9bb2a37cb88) 



     ```SQL 
     Select Region, count(CustomerID) as Total_cancellations
     From CustomerSEG
     Group by Region 
     Order by Total_cancellations DESC 



     
![Cus 9](https://github.com/user-attachments/assets/041741ec-2a4c-4ede-9e66-c80f9a03cbfe)  



     ```SQL 
     Select Canceled, count(*) as Total_Subscriptions
     From CustomerID 
     Group by Canceled 



![Cus 10](https://github.com/user-attachments/assets/6f5d45d2-fc3b-4af0-94ca-54b14c0c3f05)  


---






## Data Visulization 
---

Data Visualizations helps to quickly identify patterns, spot trends, and convey actionable insights to stakeholders in a clear and engaging way. Here are several effective types of visualizations and techniques you can use to analyze and communicate your customer segmentation data; 

  - A line chart could show the retention rate of customers who signed up in different months (e.g., customers who joined in January vs. March) over a 12-month period.

  - Pie chart: Show the breakdown of customers based on subscription plan (e.g., Basic, Premium, Free Trial).

  - Bar chart: Visualize the number of customers in different segments.



![Customer Segmentation PowerBI](https://github.com/user-attachments/assets/b435b1b7-7f82-4d9b-8145-06001fff5358) 



Effective data visualizations empower to make data-driven decisions, communicate findings clearly, and improve customer segmentation strategies. 



|Name:|Idemudia|Esther|
|-----|--------|------|
|TechSkill:|Data|Analysis| 

