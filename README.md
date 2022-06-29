# financial-complaints-dashboard
### Abstract/Keywords:

With the advent and advancement of technology, data is rapidly becoming one of the driving forces behind global economy. Every enterprise deal with a lot of data, which magnifies the difficulties of seeking information which is most relevant to their problems. Hence, it seems that the institutions make a mistake of wasting time measuring too many things. The increasing amount of data and the need for daily monitoring and evaluation lead to the development of management applications with graphical data analysis known as Dashboards, which is a tool that allows the alignment of business processes and strategies implementation. Dashboards are more than a collection of indicators and graphics; they are found in different forms and interfaces. Dashboards answer to many questions of the organization and are addressed to different types of audiences. Before creating a Dashboard, we must answer the following questions: who is our audience, what decisions should be taken after the analysis, in what context will be used, how often should be measured the indicators? Once an enterprise has identified a need for a dashboard, managers must go through the process of defining what they will include in their dashboard (key risk indicators and key performance indicators). In this project, we attempt to create a financial complaints dashboard, highlighting types and number of complaints received by Cumulus Financial institution.

#### Keywords: Dashboards, Data Visualisation, financial, data, dataset, Tableau Public


### Introduction:

#### Background:

Everyone is familiar with financial institution, nearly all of us have a relationship with a bank. Most of us, at the very least, have a savings account and a debit card, while others might have credit cards or various loan related products. Irrespective of the type of product, retail consumers have long term relationships with their banks / financial institutions. The effectiveness of the relationship between consumer and the financial institutions continues to depend upon the customer service provided by these institutions, a service that is quick, accurate and transparent as much as possible. Customer complaints are a rich source of information in terms of problems as seen from a customer point of view, towards the services and products offered from the institutional side. An effective analysis of such information will enable the institutions to forecast and identify the problems, and enable themselves with the capacity to take better action upon them.
The purpose of this project is to study the complaints received by Cumulus Financial and create a dashboard showcasing our findings.


Problem Statement:

Consider a dataset, inspired by real world data- real world fake data (RWFD) consisting of more than thousands records of the Cumulus Financial company. Analyse the given data carefully and derive information regarding the financial complaints made by the customers. Design a creative dashboard, showcasing the insights gained and providing an overview of the information obtained in a concise and clear manner. 
           


## Software and Hardware Requirement Specification:

### Method:

We adopted the following method to build our dashboard:
●	We obtained our real world fake dataset (RWFD) from data world website and studied it. There were 17 columns- complaint ID, date submitted, product, sub-product, issue, sub-issue, company public response, company, state, ZIP code, tags, consumer consent provided, submitted, date received, company response to consumer, timely response and consumer disputed.
●	Product column gave us information as to which products of the company face the most issues; Issue column gave us the information about the most common issues faced by the consumers. We understand what is the company’s response to the consumer and if the consumer disputed to the action taken by the company. We find how much time the company takes to respond to the issue and if it is a timely response.
●	We used calculated fields to create four KPIs- Timely Response (depicting the number of times company responded in time), Complaints (number of total complaints), Resolved at no cost (showing the percent of issues resolved without monetary aid) and Disputed rate (depicting number of times consumer disputed action taken by company).
●	We added a calendar to view and analyse data trends at different intervals of time. 
To create a calendar:
1.	Create a parameter to set the min and max for the date range.
2.	Create another list parameter to select month and then create a month filter to filter the data according to the month selected in month parameter.
3.	Drag the date to columns and rows; change the level to weekday and week respectively.
4.	Create two measures for start date and end date.
5.	Create a measure for date selection (IF [Select Start & End Date] = "" THEN STR([Date]) ELSEIF CONTAINS ([Select Start & End Date],";") THEN STR([Date]) ELSEIF [Date]<=DATE ([Select Start & End Date]) THEN STR([Date]) ELSE [Select Start & End Date] +";"+STR([Date]) END)
6.	Create another measure as date range color for coloring the selected date range IF [Select Start & End Date] = '12/1/2011;10/13/2020' 
THEN "Reset" ELSEIF [Date] = [Date Start] or [Date] = [Date End] THEN "selected" ELSEIF [Date]>[Date Start]and [Date]<[Date End]THEN "in range" ELSE "not in range" END )
7.	Drag data range color to shape shelf and select square and data range selection to detail shelf.
8.	Drag the weekday(date) to color shelf and day(date) to text shelf.
9.	Create a measure for false and true and then create set on false to show the date range that is in / out of the selection. Drag the false set to filter.

●	We used line chart to show the number of complaints in a year on quarterly basis. Also used bar chart to show the intake trends (the way consumers registered their complaints) and donut chart to show customers across different groups. Used a bar chart to show Product Trends- the top five products of the company which attract the most complaints
●	Line charts depict number of complaints received under Banking services, Credit-Debit card, Debt collection, Mortgage, Student loan and Vehicle loan. These sheets then are displayed in one dashboard.
●	Bar charts are used to show the total values of complaints received under every product and total number of queries under each Issue. The information was obtained by Product and Sub product, and Issue and Sub issue columns.

●	A hexagonal map shows the trend across different states. Bar charts show the states which had the highest number of complaints and top issues by states. 
#### To create a hexagonal map, we followed the following steps:
	Added the hexagon shape to the Tableau shapes repository.
	Created a file of dimensions of rows and columns with respect to each tile (representing state). The file would align the hexagon tiles to hexagon map.
To build the map:
1.	Add Row to Rows
2.	Edit the axis for Rows and reverse the scale
3.	Add Column to Columns
4.	Change the mark to Shapes
5.	Choose the custom hex shape that you added to your repository
6.	Drag Abbreviation to the label, set the vertical and horizontal alignment to centre, turn on allow labels to overlap other marks
7.	Hide the headers
8.	Adjust the size to get the preferred amount of white space.
9.	Add the worksheet to the dashboard and resize until the spacing is correct.

•	We complied all the visualizations in 6 separate dashboards each dashboard represents different layers of data. Navigation buttons are added to switch between the dashboards which further enhance the user interactivity.

## Programming/Working Environment:

We did not use any programming language to run our queries, as Tableau offers drag-and-drop functionalities for building charts and dashboards.

## Requirements to run the application:

The Dashboard created in this project was conducted with Tableau Public. Tableau Public enables interactive data visualization and focuses on business intelligence. Tableau Public allows the creation of many types of graphs that can be combined in dashboards and distributed on the internet. Currently used in all areas, Tableau Public is easily accessible and does not require programming skills. Among the advantages of using Tableau Public, we can mention: 
●	Speed – is the most important strength of Tableau Public. It is able to analyse millions of rows and provide an answer in few seconds, enabling decision making in real time. 
●	Ease of use – based on the drag and drop option. Most of times, the graphics are created by importing an Excel file. 
●	Engaging and interactive Dashboards – enables creation of smart charts and graphs. 
●	Direct connection to databases (Google Analytics, MySQL, Microsoft PowerPivot, Excel, etc.) 
●	Easy sharing – can be easily distributed on internet and mobile devices. 
●	Popular Tool of Business Intelligence. 

## Database connections and analysing
•	We have used real world fake dataset to draw information and create dashboard accordingly.
•	The data covers the year span of 10 years, ranging from 1st December 2011 to 13th October 2020.
•	The most common issue that the customers faced was related to credit and debit cards, with banking account services following closely behind. Under banking services, people had maximum number of problems with checking accounts. 
•	The institute responded in a timely manner in most of the cases (98.05%), with customers not disputing the response for majority of the time, disputed rate standing at 9.75%.
•	50% of the customers registered their complaints via web, while some customers also opting different means like, referral, phone, postal mail, fax and email. 
•	Highest number of complaints were registered in the state of California (12, 107), with the most common issue being related to credit and debit cards. New York City follows behind with 6,841 complaints.

## Program’s Structure Analysing and GUI Constructing 

## REAL WORLD FAKE DATASET           


ATTRIBUTES IN THE DATASET ARE:
1.	Date sent to company 
2.	Issue
3.	Sub- Issue
4.	Product
5.	Sub-Product
6.	State
7.	Submitted via
8.	Tags
9.	Timely response
10.	Zip Code
11.	Company
12.	Complaint ID
13.	Company public response
14.	Company response provided?
15.	Customer disputes
16.	Data Received 



## Descriptive Statistics Using Tableau 

The substage of data understanding is summarizing the attributes of the data in the form of visuals and graphs which could give a quick reference to its pattern of distribution. Using the visual way is advantageous in understanding the data, patterns, trend and overall distribution for the dataset.

### OVERVIEW

 
Overview dashboard sums up the different layers of data and helps to track major aspects with key performance indicators. As per the analysis out of 75k complaints received over 98.05% complaints were timely responded and about 85% complaints were closed with no monetary relief with customer disputed rate less than 10%. In May 2018 was the peak period in terms of no. of complaints registered. To track the progress and trends over time we can compare the data using calendar. The product trends, intake trends and customer tags trends can be viewed at a user specified data range. At product level highest number of complaints are registered for credit and debit card related issues followed by banking account services. About 50% customers registered their complaints via web. Detailed view of each layer has been described in 5 different dashboards which have be viewed with the help of navigation buttons.


### PRODUCT TRENDS 

Products offered by these financial institutions are segregated as mortgage, credit Debit card services , debt collection, student loan, Vehicle loan, and banking account services


 


As per Research and Analysis  Credit-Debit Card services being the highest distinct count of complaints for 427 complaints followed by Banking Services with the count of 398 complaints. Conventional home Mortgage is the third product issue with the count of 178.  Student Loan , debt collection , vehicle loan are the next set in terms of complaints with the rest of products put together make to a very small percentage. At the end, coming to conclusion Banking services leading to the increase number of complaints in these categories throughout the data trend.
             

### GEOGRAPHICAL TRENDS


 


Talking about statistics Figure shows  geographical trends i.e. the state wise distribution of the complaints with California being the highest recorded consumer complaints with 12,107 followed by New York and Florida with a count of 6,841and 7,750 respectively. Fourth being Texas with 5,537 complaints registered overall. The distribution looks to be scaling across the country from west to east of the united states. 
However, there are complaints which don’t have a note of the state from which these complaints have been registered and fall under null state. Then shows the product wise over all complaints received from the customer. General Credit-Debit card services has the maximum collection of the complaints with count of 19,176 followed by Banking Services  - checking accounts complaints count at 18,266



### PRODUCT DETAILS

 


According to Statistics we have six different products named mortgage, credit Debit card services , debt collection, student loan, Vehicle loan and Banking Account services with  different Sub product Breakouts. On aggregating Credit or Debit card has the highest complaints of data count of 29,417 with 7  sub Product Breakouts in which general credit or debit card has the highest statistics of count 19,176. 


### ISSUE DETAILS 

The number of complaints referring to the issue and Sub issue Breakout according to  products that are  mortgage, credit Debit card services , debt collection, student loan, and  Vehicle loan, and banking account services.
 
The Banking services contain the largest amount of complaints in managing an account with the sub Issue Breakouts like Deposits and with drawl’s , Problem using a debit or ATM card, Banking errors etc,. The  2nd highest number of complaints are related purchase shown on  statement done by credit or debit card with the count of 3,365  for which Sub issue breakout are that credit card company isn’t resolving a dispute about a purchase on your statement, credit was charged for something you did not purchase with the card, Overcharged for something you did purchase with the card. Following with continued attempt  in Billing Disputed at the count of 3,203 with general sub Issue Breakouts with the issue label of credit and debit services . Student loan, vehicle loan and debt collection have very less percentage, and don't have a considerable affect. The financial institution has responded to customer's issues in a number of different manner which come under seven 7 categories (not counting the in progress issues)- closed issue, closed issue without monetary relief, closed issue with monetary relief, closed issue with explanation, closed issue with relief, closed issue without relief and untimely response.

            



### TICKETS 

 

 All Tickets dashboard provides the general overview of all data covering major fields like complaint id, respective states, date when issue was received, product, customer issue and how company responded to the issue etc




### Limitations:

●	While the information is accurate in analysing situations, visualization of the data can just give us the estimation. It might be easy to convert large datasets into graphical and pictorial format but sometimes this representation can lead to speculations. 
●	Since basic formation of dashboard happens with human interface, the insights and perception gained may be one-sided. The individual may focus on just a significant portion of data or even skip central information, which can lead to biased results. 
●	A dashboard created from a dataset, can’t offer assistance in deciphering the intent, which means different audiences may interpret it differently.

### Conclusions:

One of the most popular sayings of the modern world is – “Data is the new oil”. This statement is proven true when we understand the amount of data that is generated in a day. The amount of data in the world was estimated to be 44 zettabytes at the dawn of 2020. It is physically impossible to keep track of large amounts of data and derive useful information from it. Data Visualization is one such field, which helps us to understand the data and visualize it, enabling us to make better decisions, and interactive dashboards, its most important tool. Dashboards might be implemented at all the levels of the institutions, as a tool that changes the business culture. One of the most important benefits of using Dashboards is the fact that information obtained from millions of bytes of data is displayed on a single screen, analysing which, people can make decisions and undertake actions to mitigate the risks and improve the performance of their institution. 
Tableau Public is a powerful tool for creating interactive Dashboards, that analyses large amounts of data in seconds. Although, dashboards provide great insights, it can only provide speculation and often shows us only an estimate. In order to solve the problem, we must use the information gained and work on an appropriate solution accordingly.
From our financial complaints dashboard, we understand what are the main problems consumers face, and how does the company- Cumulus Financial resolve them. In order to provide better customer service to its clients, the institution must focus on the information gathered, and proceed with an appropriate solution focusing on areas needing most attention.
 

### Future Scope:

This project was initiated in order to better understand the data of Cumulus Financial and how does the institute respond to customer queries and complaints. The dashboard can easily be updated with new data. This project has been made to suggest and develop some tools, which could be useful to the institute. The findings obtained from the dashboard can help improve customer services and experiences, thereby strengthening the relationship between the financial institution and it's customers. The theory and understanding obtained from the project can be applied to different data representing different industries or enterprises.




                          




## Bibliography/References                                   

[1]	Dataset: https://data.world/markbradbourne/rwfd-real-world-fake-data.

[2]	L.Ryan “Visual Data Storytelling with Tableau”, First Edition, July 2018.

[3]	Tableau: https://public.tableau.com/app/profile/anshika4020/viz/FinancialComplaintsDashboard_16564970063090/OverView?publish=yes

[4]	https://www.sirvizalot.com/2015/11/hex-tile-maps-in-tableau.html
