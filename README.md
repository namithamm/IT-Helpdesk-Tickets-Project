# IT Helpdesk Ticket Performance Analysis

IT Helpdesk Performance Analysis is a Python and Pandas project that analyzes IT support tickets to identify trends in ticket volume, resolution time, SLA breaches, team performance, and customer satisfaction. The project uses data analysis and visualization to generate insights and improve helpdesk efficiency.




## Project Overview
This project focuses on analysing IT helpdesk ticket data to understand the performance of an IT support system. The analysis examines ticket volume, ticket categories, priorities, SLA performance, response time, resolution time, support-team performance, agent performance, customer satisfaction, support channels, locations, and monthly trends.

The project was completed in two major stages:

Data Cleaning and Preprocessing Exploratory Data Analysis and Visualization.

Python libraries such as Pandas, NumPy, Matplotlib, Seaborn, and Plotly were used for data manipulation, analysis, and visualization.
The main objective is to identify operational strengths and weaknesses in the helpdesk and provide insights that can help improve SLA compliance, resolution efficiency, and customer satisfaction.





## Dataset Description
The dataset contains 3,000 IT helpdesk tickets and 15 columns. The main variables include:

>> ## Column                 >> ## Description
>> ticket_id                 >> Unique identifier for each ticket
>> created_date              >> Date and time when the ticket was created
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



## Exploratory Data Analysis
After cleaning, the project analysed the dataset using different statistical calculations and graphs.
The analysis can be divided into several areas.


## Overall Ticket Analysis 
There are 3,000 tickets in the dataset. Most tickets were Resolved, with 1,981 tickets. However, 477 tickets were Reopened, which is an important operational point because reopened tickets can indicate that the original solution did not completely address the customer's issue. The helpdesk is successfully resolving a large majority of tickets, but the number of reopened tickets suggests that there is still room to improve first-time resolution and solution quality.

>> Ticket Category Analysis: Software generated the highest number of tickets, with 583 tickets, while Security Incident had the lowest, with 184 tickets. Software-related problems represent the largest source of helpdesk workload. Therefore, software troubleshooting, user training, documentation, and self-service solutions could potentially reduce the number of recurring software tickets.

>> Priority Analysis: Low-priority tickets are the largest group, while Critical tickets are the smallest. Although Critical tickets represent a relatively small portion of the total workload, they require faster attention because their SLA targets are more demanding.

>> Location Analysis: HQ - Dubai has the highest ticket volume, followed by Remote users. The high volume from HQ - Dubai is expected to require significant helpdesk resources. However, Remote users are particularly important because their SLA breach rate is higher.

>> Support Channel Analysis: Email is the most frequently used support channel, closely followed by the Self-Service Portal. Walk-in has the lowest volume. Although Email has the highest volume, the Self-Service Portal has the highest customer satisfaction, suggesting that encouraging users to use self-service could be beneficial.

>> SLA Analysis: SLA performance is one of the most important parts of this project. Out of 3,000 tickets: 2,258 tickets did not breach SLA 742 tickets breached SLA Overall SLA breach rate = 24.73% This means approximately one-quarter of the tickets did not meet their defined SLA target. Although the average resolution time is below the overall average SLA target, SLA performance is still an important weakness because 24.73% of tickets breached SLA.

>> SLA Breach by Priority: Critical tickets have the highest SLA breach rate at 29.55%. Critical incidents are the most difficult to resolve within their SLA targets. Since these tickets have high business importance, the helpdesk should give them additional monitoring and escalation support.

>> SLA Breach by Category: Email has the highest SLA breach rate at 31.67%. Interestingly, Software has the highest number of total SLA violations (134) because it also has the highest ticket volume. Hardware has 122 violations and Access Management has 105. This shows why both breach rate and number of breaches are useful: Email has the highest percentage of tickets breaching SLA. Software has the highest number of SLA violations.

>> SLA Breach by Support Team: Security Team has the highest SLA breach rate, while Network Ops has the lowest. Network Ops demonstrates relatively strong SLA performance. Security Team may need additional investigation to determine whether ticket complexity, workload, or resource allocation contributes to its higher breach rate.

>> SLA Breach by Location: Remote users have the highest SLA breach rate at 27.38%, while HQ - Dubai has the lowest at 21.29%. Remote support appears to be an important area for improvement. Remote users may experience additional difficulties related to connectivity, access, or communication.

>> SLA Breach by Channel: Chat has the highest SLA breach rate, while Phone has the lowest. Chat requires attention because it combines a relatively high SLA breach rate with the lowest customer satisfaction.

>> Response Time Analysis: The average first response time is: 6.34 hours The average resolution time is: 21.77 hours The results show a clear priority-based response pattern. Critical tickets receive attention much faster than Low-priority tickets. This indicates that the helpdesk is prioritizing urgent incidents appropriately.

>> Resolution Time by Category: Email has the longest average resolution time at 23.98 hours, while Application Support is the fastest at 20.08 hours. Email issues are a major concern because Email has: Highest ticket volume Highest SLA breach rate Longest average resolution time among categories Therefore, Email-related incidents should be one of the primary improvement areas.

>> Resolution Time by Support Team: Network Ops has the fastest average resolution time, while Service Desk L1 has the longest.

Agent Performance The analysis also compared average resolution time among agents. The fastest average resolution was achieved by: I. Rossi – 19.22 hours The slowest average resolution was: F. Torres – 23.91 hours The project therefore provides a way to identify differences in individual agent performance. However, these figures should be interpreted carefully because agents may receive different types, priorities, and volumes of tickets.

SLA Target vs Actual Resolution The average SLA target is: 27.41 hours The average actual resolution time is: 21.77 hours This means the overall average resolution time is approximately 5.63 hours below the average SLA target. At an overall level, the helpdesk is resolving tickets faster than the average SLA target. However, this does not mean every ticket meets its SLA, as demonstrated by the 24.73% overall breach rate.

Customer Satisfaction Analysis The average customer satisfaction score is: 3.99 / 5 There were 2,523 recorded satisfaction responses. This represents generally positive customer feedback, but there is still room for improvement.

Customer Satisfaction by Team Service Desk L1 has the highest team satisfaction score at 4.03.

Customer Satisfaction by Channel The Self-Service Portal has the highest satisfaction score, while Chat has the lowest. The Self-Service Portal appears to be an effective support channel from a customer satisfaction perspective. Chat, on the other hand, should be investigated because it has: Lowest satisfaction, Highest SLA breach rate, Longest average resolution time

Resolution Time vs Customer Satisfaction The correlation between resolution time and customer satisfaction is: -0.27427 This indicates a negative relationship between resolution time and satisfaction. In simple terms: As resolution time increases, customer satisfaction tends to decrease. This is an important business insight because it demonstrates that improving resolution speed can potentially improve customer experience. The relationship is not extremely strong, so resolution time is not the only factor influencing satisfaction.

SLA Breach vs Customer Satisfaction Customers associated with tickets that did not breach SLA had an average satisfaction of 4.21, whereas tickets that breached SLA had an average satisfaction of only 3.27. SLA compliance is strongly associated with customer satisfaction in this dataset. Therefore, reducing SLA breaches should not only improve operational performance but may also improve customer experience.

Monthly Ticket Volume Key findings May: highest ticket volume – 267 December: lowest ticket volume – 225 The project also notes that May's increase is not large enough to be classified as an unusual outlier using the standard-deviation approach.

Monthly SLA Performance April had the highest SLA breach rate at 29.12%, while September had the lowest at 20.00%. This monthly analysis can help management identify periods when additional staffing or operational monitoring may be useful.

Overall Channel Performance Phone has the strongest operational performance, with the lowest SLA breach rate and fast resolution. Chat is the weakest overall channel because it has the longest resolution time, highest SLA breach rate, and lowest satisfaction.

Overall Location Performance HQ - Dubai has the highest ticket volume. HQ - Dubai also has the lowest SLA breach rate. Singapore has the longest resolution time. New York has the highest customer satisfaction. Remote users have the highest SLA breach rate.
