# IT Helpdesk Ticket Performance Analysis

##IT Helpdesk Performance Analysis is a Python and Pandas project that analyzes IT support tickets to identify trends in ticket volume, resolution time, SLA breaches, team performance, and customer satisfaction. The project uses data analysis and visualization to generate insights and improve helpdesk efficiency.




**Project Overview**

This project focuses on analysing IT helpdesk ticket data to understand the performance of an IT support system. The analysis examines ticket volume, ticket categories, priorities, SLA performance, response time, resolution time, support-team performance, agent performance, customer satisfaction, support channels, locations, and monthly trends.

The project was completed in two major stages:

Data Cleaning and Preprocessing Exploratory Data Analysis and Visualization

Python libraries such as Pandas, NumPy, Matplotlib, Seaborn, and Plotly were used for data manipulation, analysis, and visualization.

The main objective is to identify operational strengths and weaknesses in the helpdesk and provide insights that can help improve SLA compliance, resolution efficiency, and customer satisfaction.





**Dataset Description**
The dataset contains 3,000 IT helpdesk tickets and 15 columns. The main variables include:

**Column**              **Description**
ticket_id                 Unique identifier for each ticket
created_date              Date and time when the ticket was created
resolved_date	            Date and time when the ticket was resolved
category	                Type of IT issue
priority	                Priority level of the ticket
sla_target_hours	        Target time according to SLA
first_response_hours	    Time taken to provide the first response
resolution_time_hours	    Total time taken to resolve the ticket
sla_breached	            Indicates whether the SLA was breached
status	                  Current ticket status
assigned_team	            Team responsible for the ticket
agent_name	              Agent handling the ticket
location	                Location associated with the ticket
channel	                  Support channel used
customer_satisfaction	    Customer satisfaction rating
The dataset contains 3,000 records, with 2,862 non-null resolved_date values and 2,523 customer satisfaction responses.




**Data Cleaning and Preprocessing**
The first stage of this project was data cleaning. This was important because reliable analysis depends on having properly structured and consistent data.

>> Step 1: Importing libraries
The project used:
Pandas
NumPy
Matplotlib
Seaborn
Plotly
Pandas and NumPy were used for data manipulation and numerical analysis, while Matplotlib, Seaborn, and Plotly were used for visualization.

>> Step 2: Loading the dataset
The original IT helpdesk dataset was loaded into a Pandas DataFrame.

>> Step 3: Understanding the dataset
The dataset was examined using:
head()
tail()
shape
info()
dtypes
describe()
This established that the original dataset contained 3,000 rows and 15 columns.

>> Step 4: Standardizing column names
Column names were cleaned by:
Removing leading/trailing spaces
Converting names to lowercase
Replacing spaces with underscores
For example:
Ticket ID → ticket_id
This makes the dataset easier to work with in Python.

>> Step 5: Checking missing values
Missing values were assessed for every column.
The important missing values were:
resolved_date: 138 missing values
customer_satisfaction: 477 missing values
The project identified that missing satisfaction values could occur because a customer did not provide a survey response. In particular, the notebook notes that a Reopened ticket can have a missing satisfaction score without making the entire record invalid.
Therefore, these missing satisfaction values were not automatically treated as erroneous data.

>> Step 6: Checking categorical values
Unique values were checked for variables such as:
Category
Priority
Status
Assigned team
Agent
Location
Channel
Customer satisfaction
This helps identify inconsistent or unexpected categories.

>> Step 7: Converting date columns
created_date and resolved_date were converted from strings into datetime format.
This was necessary for performing time-based analysis such as monthly ticket volume and monthly SLA breach rates.

>> Step 8: Removing duplicate records
Duplicate records were checked and removed using:
df.drop_duplicates()

>> Step 9: Cleaning text fields
Spaces were removed from text columns using string stripping. This helps prevent problems caused by inconsistent whitespace.

>> Step 10: Saving the cleaned dataset
After preprocessing, the cleaned dataset was saved as:
it_helpdesk_tickets_cleaned.csv
The cleaned dataset was then used for the analysis stage.



**Exploratory Data Analysis**

After cleaning, the project analysed the dataset using different statistical calculations and graphs.
The analysis can be divided into several areas.
