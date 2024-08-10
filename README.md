# SUPERMARKET-PROJECT-DASHBOARD
# ABOUT THE PROJECT

This project provides a comprehensive analysis of grocery sales for different supermarket in Tamil Nadu, India, focusing on various aspects of the sales data to derive actionable insights. By analyzing the data, you can identify top-performing regions, product categories, and customers, as well as areas that need improvement.

The dashboard created from this analysis will be a powerful tool for decision-makers to understand the supermarket’s performance, identify opportunities for growth, and implement strategies to optimize sales and profitability across different regions and product categories in Tamil Nadu.

## INSTALLATION

```python
pip install numpy
pip install pandas
pip install matplotlib
```

## IMPORTING LIBRARY

```bash  
import numpy

import pandas

import matplotlib
```


## Key Objectives of the Project
1.  Sales Performance by Dayofweek
2.  Customer Insights- sales by customer name
3.  Strategic Insights- Category by profit
4.  Strategic Insights- Category by sales
5.  Strategic Insights- Category of sales by year
6.  Strategic Insights- Discount Optimization 


## Steps followed 

- Step 1 : Load Anaconda Prompt.
- Step 2 : In Jupyter homepage, Upload the dataset which is an csv file.
- Step 3 : Go to New to create a new jupyter notebook and rename the notebook.
- Step 4 : Import the libraries(Numpy,Pandas and Matplotlib), Numpy for working the numerical operations. Pandas to deal with changing the data type and the error values, matplotlib for plotting.
- Step 5 : Import the csv file into the notebook to check the information and setting the index as Order ID.

sales=pd.read_csv("C:/Users/MOORE/Desktop/Supermart Grocery Sales - Retail Analytics Dataset.csv",index_col='Order ID')
sales

- Step 6 : To check the datatype of the dataset, use variable name.info().

sales.info()

- Step 7 : Using datetime function, change the date in object type to datetime.

sales['Order Date']=pd.to_datetime(sales['Order Date'])

- Step 8 : Creating a new column for dayname using

sales['Day_Name']=sales['Order Date'].dt.day_name()

## Solution 1

- Step 9 : Using .groupby(), to get the sum of sales for each day.

Daysales=sales.groupby('Day_Name')['Sales'].sum()

- Step 10 : Extracted the index and values for plotting.
- Step 11 : Proceed to plotting the graph using barh chart with fontsize,fontweight,fontstyle and color.
    
    ![Screenshot (16)](https://github.com/user-attachments/assets/1a581ef3-99c0-4448-b0e6-50bd8a244ea2)



## Solution 2

- Step 12 : Using sort_values to get the top 6 customer name by sales in the dataset. 

Top6cust=sales.sort_values('Sales',ascending=False).head(6)

- Step 13 : Using groupby to get the sum of sales by customer name.

Top6=Top6cust.groupby('Customer Name')['Sales'].sum()

- Step 14 : Extracted the index and values from the groupby result for plotting.
- Step 15 : Plotted the graph using pie chart setting autopct, explode and shadow.

![Screenshot (17)](https://github.com/user-attachments/assets/0c45e0a9-ecca-426a-baa0-4e531bbbe842)

## Solution 3

- Step 16 : Using sort_values to get the top 10 category by profit in the dataset. 


Top10cat=sales.sort_values('Profit',ascending=False).head(10)

- Step 17 : Using the groupby function to get the sum of profit by category.

Cat=Top6cust.groupby('Category')['Profit'].sum()

- Step 18 : Extracted the index and values from the groupby result for plotting.  
- Step 19 : Plotted a line chart using plot setting the color as red, marker as o.


![Screenshot (18)](https://github.com/user-attachments/assets/0e200078-6d5b-45c8-9d04-d72be8558561)




## Solution 4

- Step 20 : Plotting the chart with seaborn.
- Step 21 : Using the xlabel as Sub CATEGORY and ylabel as sum of sales.

![Screenshot (19)](https://github.com/user-attachments/assets/1edb5e3c-4bb3-4f0c-8208-89f5766eba80)



## Question 5
- Step 22 : Splitting the year from the Order Date.

sales['Year']=sales['Order Date'].dt.year

- Step 23 : Using the groupby function to get the sum of sales by year.

Year=sales.groupby('Year')['Sales'].sum()

- Step 24 : Extracted the index and values from the groupby result for plotting.  
- Step 25 : Plotted using pie chart, setting autopct, explode and shadow

![Screenshot (20)](https://github.com/user-attachments/assets/b758513e-3612-4a70-944f-8e76685d01f7)


## Solution 6

- Step 26 : Plotting the chart with seaborn,setting the data as sales and palette as winter.
- Step 27 : Giving the chart a title,'Region by Discount', with fontsize,fontweight,fontstyle.
- Step 28 : Using the xlabel as Region and ylabel as Discount.

![Screenshot (21)](https://github.com/user-attachments/assets/bae5b10b-8ff4-412d-9bcc-e5965d2ee48c)
