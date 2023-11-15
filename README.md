# PWC Power BI Virtual Internship (Call Center Trend Analysis)
![Pwc Virtual Internship - Call Center Trend Analysis](https://github.com/sid-25L/PWC-Task-1/assets/137102972/2ddb1f41-58c3-4d93-93b2-79392a0ad909)



# Table of Contents :
- [Problem Statement](https://github.com/sid-25L/PWC-Task-1/edit/main/README.md#problem-statement)
- [Datasource](https://github.com/sid-25L/PWC-Task-1/edit/main/README.md#data-source-)
- [Data Preparation](https://github.com/sid-25L/PWC-Task-1/edit/main/README.md#data-preparation-1)
- [Data Modelling](https://github.com/sid-25L/PWC-Task-1/edit/main/README.md#data-modelling-1)
- [Data Analysis(Dax)](https://github.com/sid-25L/PWC-Task-1/edit/main/README.md#data-analysis-dax-1)
- [Data Visualization Dashboard](https://github.com/sid-25L/PWC-Task-1/edit/main/README.md#data-visualization-dashboard-1)
- [Insights](https://github.com/sid-25L/PWC-Task-1/edit/main/README.md#insights-1)


 # Problem Statement
In this Project Create a dashboard in Power BI for Call Center Manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset. 

Possible KPIs include :

•	Overall customer satisfaction

•	Overall calls answered/abandoned

•	Calls by time

•	Average speed of answer


# Data source : 

Dataset Used is Provided by [Pwc](https://user-images.githubusercontent.com/137102972/283133673-2ddb1f41-58c3-4d93-93b2-79392a0ad909.png) and call center dataset.

Dataset:(https://github.com/sid-25L/PWC-Task-1/blob/main/01%20Call-Center-Dataset.xlsx)


# Data Preparation
1.	Data Transformation: Used Power Query to transform a "Call Center Trends" dataset with 10 columns and 5000 rows.

2.	Handling Null Values: Replaced any null values in the dataset with zeros for consistency

3.	Data Type Validation: Ensured each column in the dataset has the correct data type for accurate analysis.



# Data Modelling
Prepared some temporary table such as 
1.	`Month of Year Table`: Create a table that maps numerical months to their corresponding text representation (e.g., 1 to "January"). This allows for more readable and user-friendly reports when analyzing data over time.

2.	`Satisfaction Rate Table`: Design a table that categorizes numeric satisfaction ratings into descriptive categories like "Poor," "Average," "Satisfied," "Good," and "Excellent." This table simplifies the interpretation of satisfaction data and aids in reporting.

3.	`Days Table`: Establish a table that translates numerical days into their textual representation (e.g., 1 to "Monday"). This makes it easier to understand and analyze data based on days of the week.

4.	`Timeslot Table`: Develop a table categorizing time slots into broader categories like "Morning," "Afternoon," and "Evening." This simplifies time-based analysis, providing a more intuitive understanding of data patterns.

5.	`Measures Table`: Create a table to store calculated measures or key performance indicators (KPIs) used in your analysis. This centralizes the definition of these measures, promoting consistency and easy reference throughout your data model.

6.	Documentation and Relationships: Document the purpose and relationships of each table in a clear and concise manner. Ensure that relationships between tables are well-defined, making it easy for users to navigate and understand the structure of your data model.


 ![Capture](https://github.com/sid-25L/PWC-Task-1/assets/137102972/d2fed771-8c47-4a88-9ea1-0c0611e224b9)


# Data Analysis (DAX)
Measured used in visualization are: 
- Average satisfaction Rate = `AVERAGEX(FILTER(call_center_table,'call_center_table'[Answered (Y/N)]="Yes"),call_center_table[Satisfaction rating-ID])`
  
- AVG speed of Answers = `AVERAGEX(FILTER(call_center_table, 'call_center_table'[Answered (Y/N)] = "Yes"),call_center_table[Speed of answer in seconds])`

- Call resolution Rate = `DIVIDE('Table'[Call Resolved],'Table'[Total calls],0`

- Call Resolved = `COUNTROWS(FILTER('call_center_table','call_center_table'[Resolved] = "Yes"))`

- Calls Unresolved = `COUNTROWS(FILTER('call_center_table','call_center_table'[Resolved] = "No"))`

- Total calls = `COUNT(call_center_table[Call Id])`

- Total Calls Answered = `COUNTROWS(FILTER('call_center_table','call_center_table'[Answered (Y/N)] = "Yes"))`

- Total Calls Unanswered = `COUNTROWS(FILTER('call_center_table','call_center_table'[Answered (Y/N)] = "No"))`


# Data Visualization Dashboard:
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:
Shows visualizations from Call Center Trends 
![Oveview](https://github.com/sid-25L/PWC-Task-1/assets/137102972/5d855462-dc46-4884-b533-090fcb009fb1)
![Agent's performance](https://github.com/sid-25L/PWC-Task-1/assets/137102972/04fa2c8e-6aa8-4245-b004-39750e707803)

 
# Insights
- Total Calls:	Handled a total of 5000 calls.

- Calls Resolution Rate: Achieved an impressive resolution rate of `72.92%`.

- Customer Satisfaction:	Most satisfaction ratings are above 3, with an `average rating of 3.40`.

- Monthly Resolution Rate: Call resolution rates are `highest in January`, followed by February and March.

- Call Distribution by Topic: Calls are `evenly distributed` among topics, each comprising around 20% of the total.
	
- Average Speed of Answers by Topic: Payment-related topics have the `highest average speed of answers at 68.20 seconds`, followed by technical support at 68.11 seconds. Streaming has the lowest at 66.89 seconds.

- Highest Call Satisfaction by Agent: 	Martha leads with the `highest satisfaction rate of 3.47``, followed by Dan and Diene.

- `Highest Call Resolution Rate by Agent: Dan takes the lead in call resolution rate`, followed by Joe and Becky.

- Fastest Average Speed of Answer by Agent: `Joe has the highest average speed of answer`.

- Morning Slot Performance:  The `morning slot received the highest number of calls and achieved the highest count of 5-star ratings`.
