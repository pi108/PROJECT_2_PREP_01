# PROJECT # 2
## Visualize me, Captain  
### Team Members
* *Swati Saxena*
* *Firdosh Patel*
* *Ann McNamara*

### This repository contains the files regarding a Website Visualization exercise conducted by our group. This folder contains the following:
1.	SQLite Database called "covidData.db".
2.	Python file called "covidData.py" that contains user-created functions. 
3.	Python file called "application.py" that cretaes api routes using the user-created functions.
4.	Folder called "static" that contains 2 folders:
    *	css - folder contains a file called "style.css" which is used to format the website.
    *	js - this folder contains a javascript file called "plots.js" which is used to create the visualizations ont eh website. 
5.	Folder called "templates" that contains a file called "index.html" which the file used to create the webpage. 
6.	File called "requirements.txt" which contains the requirements for the application to run. 
7.	A zip folder called "PROJECT_2_PREP_01.zip" which contains the above 6 files and folders, that was pushed to AWS. 
8.	A folder called "images" thatr contains images of our Website.

## Data Extraction:
This project is about a website visualtion exercise using COVID-19 data. 
<br>
As per wikipedia.org:
<br>
https://en.wikipedia.org/wiki/Coronavirus_disease_2019
<br>
Coronavirus disease 2019 (COVID-19) is an infectious disease caused by severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2). It was first identified in December 2019 in Wuhan, China, and has resulted in a global pandemic. 
<br>
Our group undertook an exercise of analyzing COVID-19 data as it pertains to all the 50 states in the United States of America. 
<br>
We extracted data from the following sources for our analysis:
<br>
https://www.kaggle.com/imdevskp/corona-virus-report
<br>
This data source had data related to actual number of new daily cases, new daily deaths, and total cumulative deaths for every county and state in the United States. 
<br>
http://www.healthdata.org/covid/data-downloads
<br>
This data source had data related to the predicted number of new daily cases, new daily deaths, and total cumulative deaths for every state in the United States. 
<br>

## Data Transformation:
We did the following to transform the data:
1.	Addressed NULL values. 
2.	Formatted the dates in a manner that would work with the flask library in python. 
3.	"Rolled-up" / summarized the dataset with actual numbers fromt he original level of State/County/Date to the level of State/Date.
4. Created a ranking for the states based on the Total Deaths Per Million of Population.

## Data Load: 
We then loaded the data into a SQLite database and called it covidData.db.

## Creation of a Python File with Functions:
We used SQL Alchemy to create functions in a python file called covidData.py. These functions allow us to extract the relevant data from the SQLite Database.

## Creation of a Python File with API routes:
We then used Flask to create API routes in a file called application.py. This file uses the functiosn created in the file called covidData.py. 

## Creation of an HTML file:
We then created an HTML file called index.html. This file contains the structure for the webpage. It also has teh relevant reference to all the underlying files that ar eused to format / style the webpage as well as dynamically create visualizations on the webpage.

## Creation of Javascript file:
We then created a Javascript file called plots.js. This file contains all the logic that controls the dynamic interactions with the visualizations on the webpage.  

## Attached below is a screenshot of the Top Half of our webpage. 
![](images/Website_Top_Half.PNG)

## Attached below is a screenshot of the Bottom Half of our webpage. 
![](images/Website_Bottom_Half.PNG)




![erd](ER_Diagram.png)

### Loading Data into Tables in the Database:
* We used a jupyter notebook to load data into the 3 tables in the database as follows:
* We loaded data from Data Frame # 1 into the table called “combined_macro_eonomic_indicators_table_daily”.
* We loaded data from Data Frame # 2 into the table called “aggregated_macro_economic_indicators_table_monthly”.
* We loaded data from Data Frame # 3 into the table called “combined_big_mac_table”.
* We ran select statements from each of the 3 tables inside the PostgreSQL database and verified that all the data is in the 3 tables.

*Please click on images to see full resolution table*

#### TABLE 1: combined_big_mac_table
<img src="/images/select_big_mac.png" 
     alt="Big Mac Table" width="500" /> 

#### TABLE 2: combined_macro_economic_indicators_table_daily

<img src="/images/select_dailypng.png" 
     alt="Daily Table" width="500" />

#### TABLE 3: aggregated_macro_economic_indicators_table_monthly

<img src="/images/select_monthly.png" 
     alt="Monthly Table" width="500" />

### Sample Query
We also extracted the actual Indian Rupee to USD exchange rate, and the implied Indian Rupee to USD exchange rate, by running a join statement joining the following tables:
* aggregated_macro_economic_indicators_table_monthly (which contains data from the FRED website).
* combined_big_mac_table (which contains data from the Economist magazine website).

<!-- <img src="/images/target_analysis.png" 
     alt="Query" width="600" /> -->
![query](/images/target_analysis.png)

## Justification for Selecting PostGreSQL over mongoDB
Justification for why we chose PostGreSQL (relational) instead of MongoDB for our ETL Project:
### Use Relational SQL Databases When:
* ACID (Atomicity, Consistency, Isolation, Durability) principles are enforced. This reduces anomalies, enforces integrity and that is why this is preferred for commerce and financial applications.
* Data structure is not changing. If you application design is solid and not expected to be changing with future requirements (at least not very often) then it is best to  proceed to use this type of construct and be confident in your data.
### Use Non-Relational No-SQL Databases When:
* Rapid Application Development is used. No-SQL database supporting rapidly changing designs and coding sprints and is perfect for more Agile settings, where requirements change often.
*  Storing large amounts of data with little to no structure. Much like expressed in the previous point, if your data requirements are not clear, bu you know that you need to store lots of data somewhere and somehow, then you can use this database type, which you can morph on the fly to match the requirement.

Based on the fact our data structure is not chaning and we want to enforce ACID principles we are confident using a relational database is a good choice for storing this data. 

# Summary
The above description demonstrates our team capability to successfully apply Extract, Tranform and Load (ETL).  
