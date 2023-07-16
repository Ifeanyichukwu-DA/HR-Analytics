# Analyzing HR Data to Improve Employee Retention and Performance
![](Intro.jpg)

## Introduction
Finding and hiring the right employees is vital, but retaining them is just as important. One of the biggest challenges facing the Human Resources department today is how to retain and develop top talent in the organization. 
This project presents the analysis of HR data using Power BI. This will enable the organization to gain insights into factors that affect employee retention and performance and identify areas for improvement. 

## Problem Statement
1. What is the number of employees across demographics?
2. What is the total attrition/departures and attrition rate across demographics?
3. What is the retention rate in the organization?
4. What factors contribute to the majority of attrition/departures in the organization?

## Skills Demonstrated
- Data Analysis Expressions (DAX): Effective use of logical, date, time functions, Filters, Calculated columns, and tables.
  Below is one of the DAX measures <br>
  ``` Attrition = CALCULATE([Hire Count], Employees_data[Attrition] = "Yes", USERELATIONSHIP('Calendar'[Date], Employees_data[DepartureDate]), NOT(ISBLANK(Employees_data[DepartureDate]))) ```
- Using field parameters.
- Data Visualization.
- Data Modeling.

## Data Sourcing
This fictional dataset was gotten from **[Kaggle](https://www.kaggle.com/datasets/patelprashant/employee-attrition)**. The dataset contained employees' demographics, attrition, and employment details.

## Data Transformation 
The HR dataset is in an Excel format and was loaded into power query on Power BI for cleaning. Firstly, I renamed the tables using "Dim" as the prefix for dimension tables and "_data" as the suffix for fact table(s). The following transformations were performed on the data;
* Corrected data type for date columns
* Replaced empty cells with **NA**
* Renamed some column headers

## Data Modeling
There are 15 tables in the dataset, although I added a calculated calendar for attrition. This was done to ease time intelligence calculations. Therefore, in total, there are 16 tables, 15 dimension tables, and one fact table (employee_data). All the tables were related since they have a matching column in the fact table to produce a one-to-many relationship and form a star schema.
***
![](Data_Model.jpg)

## Visualization
