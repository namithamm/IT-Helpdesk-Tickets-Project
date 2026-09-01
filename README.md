# IT Helpdesk Ticket Performance Analysis

IT Helpdesk Performance Analysis is a Python and Pandas project that analyzes IT support tickets to identify trends in ticket volume, resolution time, SLA breaches, team performance, and customer satisfaction. The project uses data analysis and visualization to generate insights and improve helpdesk efficiency.




**Project Overview**

This project focuses on analysing IT helpdesk ticket data to understand the performance of an IT support system. The analysis examines ticket volume, ticket categories, priorities, SLA performance, response time, resolution time, support-team performance, agent performance, customer satisfaction, support channels, locations, and monthly trends.

The project was completed in two major stages:

Data Cleaning and Preprocessing Exploratory Data Analysis and Visualization

Python libraries such as Pandas, NumPy, Matplotlib, Seaborn, and Plotly were used for data manipulation, analysis, and visualization.

The main objective is to identify operational strengths and weaknesses in the helpdesk and provide insights that can help improve SLA compliance, resolution efficiency, and customer satisfaction.





**Dataset Description**

The dataset contains 3,000 IT helpdesk tickets and 15 columns. The main variables include:

**Column**              **Description**
ticket_id	              Unique identifier for each ticket
created_date	          Date and time when the ticket was created
resolved_date	          Date and time when the ticket was resolved
category	              Type of IT issue
priority	              Priority level of the ticket
sla_target_hours	      Target time according to SLA
first_response_hours	  Time taken to provide the first response
resolution_time_hours	  Total time taken to resolve the ticket
sla_breached	          Indicates whether the SLA was breached
status	                  Current ticket status
assigned_team	          Team responsible for the ticket
agent_name	              Agent handling the ticket
location	              Location associated with the ticket
channel	                  Support channel used
customer_satisfaction	  Customer satisfaction rating

The dataset contains 3,000 records, with 2,862 non-null resolved_date values and 2,523 customer satisfaction responses.
