# PROJECT # 2
# Visualize me, Captain !!  
## Team Members
* *Swati Saxena*
* *Firdosh Patel*
* *Ann McNamara*
<br>

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
<br>
As per wikipedia.org:
<br>
https://en.wikipedia.org/wiki/Coronavirus_disease_2019
<br>
Coronavirus disease 2019 (COVID-19) is an infectious disease caused by severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2). It was first identified in December 2019 in Wuhan, China, and has resulted in a global pandemic. 
<br>
<br>
Our group undertook an exercise of analyzing COVID-19 data as it pertains to all the 50 states in the United States of America. 
<br>
We extracted data from the following sources for our analysis:
<br>
<br>
https://www.kaggle.com/imdevskp/corona-virus-report
<br>
This data source had data related to actual number of new daily cases, new daily deaths, and total cumulative deaths for every county and state in the United States. 
<br>
<br>
http://www.healthdata.org/covid/data-downloads
<br>
This data source had data related to the predicted number of new daily cases, new daily deaths, and total cumulative deaths for every state in the United States. 
<br>
<br>
https://worldpopulationreview.com/states/
<br>
This data source had data related to the population for every state in the United States. 
<br>
<br>
https://www.latlong.net/category/states-236-14.html
<br>
This data source had data related to the latitude and longitude for every state in the United States. 
<br>
<br>
https://www.50states.com/abbreviations.htm
<br>
This data source had data related to the state name abbreviations for every state in the United States. 
<br>

## Data Transformation:
We did the following to transform the data:
1.	Addressed NULL values. 
2.	Formatted the dates in a manner that would work with the flask library in python. 
3.	"Rolled-up" / summarized the dataset with actual numbers fromt he original level of State/County/Date to the level of State/Date.
4. Created a ranking for the states based on the Total Deaths Per Million of Population.

## Data Load: 
We then loaded the data into a SQLite database and called it covidData.db.
<br>
<br>

## Creation of a Python File with Functions:
We used SQL Alchemy to create functions in a python file called covidData.py. These functions allow us to extract the relevant data from the SQLite Database.
<br>

## Creation of a Python File with API routes:
We then used Flask to create API routes in a file called application.py. This file uses the functions created in the file called covidData.py. 
<br>

## Creation of an HTML file:
We then created an HTML file called index.html. This file contains the structure for the webpage. It also has all the relevant references / links to the underlying files that are used to format / style the webpage, as well as dynamically create the charts / graphs on the webpage.
<br>

## Creation of a Javascript file:
We then created a Javascript file called plots.js. This file contains all the logic that controls the dynamic interaction of a user with the webpage. This logic allows for dynamic updates to the charts / graphs based on the user's selection of a particular US state.
<br>

## Push to AWS:
We then zipped all the relevant files and folders and uploaded them to an environment on AWS using the service called "Elastic Beanstalk". This environment then provided us a URL for our webpage.
<br>
This is the URL for our webpage.
<br>
http://20200610v1-env.eba-3ip3pqzu.us-east-2.elasticbeanstalk.com/
<hr>

## Attached below is a screenshot of the Top Half of our webpage. 
![](images/Website_Top_Half.PNG)
<hr>

## Attached below is a screenshot of the Bottom Half of our webpage. 
![](images/Website_Bottom_Half.PNG)
<hr>

## Details of the webpage: 
When a user selects a state from the dropdown box in the upper left hand corner, the following items update automatically with teh relevant details for that state as follows:
1.	The panel below the dropdown box. This panel shows for the selected satte, the total number of cases, teh total number of deaths, and the total population. 
2.	The map to the right of the dropdown box. The map zooms in to the selected state. You can then use the mouse to zoome in further or zoom out. You can also mouse over the state and that will pop up a box showing the total number of deaths for that state. The state will have a color ranging from light gray to solid blue depending on the number of total deaths for that state. To the right of the map is a vertical bar which shows how the color scal changes from light gray to solid blue depending on the tototal number of deaths for the selected state.
3.	The gauge chart to the upper right of the map. This chart is created using a special javascript library called "gauge-chart". Details of this library can be found at this link:
This gauge chart shows a ranking for the state based on total number of deaths per million of population. It is a scale with a ranking of 1 to 50 where a rank of 1 means that the selected state had the lowest (best) ratio of total number of deaths per million of population, and a ranking of 50 means that the selected state had the highest (worst) ration of total number of deaths per million of population. 
4.	The pie chart to the lower right of the map. This chart shows the percentages of the total population broken down into 3 categories, total number of cases, total number of deaths, and the total number unaffected - the sum of teh 3 percentages will always summ to 100% of the population of the selected state. It is a way to visually depict the magnitude of the total number of cases and deaths compared to the magnitude of the portion of the population unaffected.
5.	The box to the left of the screen below the  panel summary which is below the dropdown box.
6.	The box in the middle of the screen below the map. 
7.	The box to the right of the screen below the pie chart.
8.	Bar chart # 1 which is below the 3 boxes mentioned in points 5 to 7 below. 
9.	Bar chart # 2 which is below Bar Chart # 1. 
10.	Bar chart # 3 which is below Bar Chart # 2. 


# Conclusions:


