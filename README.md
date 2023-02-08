<a href="https://app.powerbi.com/view?r=eyJrIjoiN2RkNGNjOTMtYmMxOC00NzY3LTg0OGEtMmY4YThlNWM5ZmMyIiwidCI6ImFlZDI3MWNkLTYzOTgtNDllZi1hOWNmLTQ4NDIyMTAxZTE0ZSIsImMiOjEwfQ%3D%3D&amp;pageName=ReportSection" target="_blank" rel="noopener"> <img class="pbi" src="https://datamatrix-ml.com/wp-content/uploads/2023/02/Power_BI_small_Logo.png" alt="Click here to open report" title="View PowerBI Report" style="width:45px;height:45px;">
View PowerBI Report</a>

<h1 id="#Pharmaceutical-Sales-Analysis">Pharmaceutical Sales Analysis</h1>
In this ‘Data Analysis’ project, we’ll analyze a global Pharmaceutical Manufacturing Company's raw sales data and draw some meaningful insights.

<img src="https://github.com/sssingh/pharmaceutical-sales-analysis-powerbi/blob/main/images/pharma-title-image.png?raw=true" width="800" height="300" />

## Features
⚡PowerBI Desktop   
⚡Query Editor  
⚡Multipage Fully Interactive Report    
⚡Report accessible on the web without PowerBI login

## Table of Contents
- [Introduction](#introduction) 
- [Objective](#objective)
- [Dataset](#dataset)
- [Solution Approach](#solution-approach)
- [Conclusions](#Conclusions)
- [How To Use](#How-To-Use)
- [License](#License)
- [Credits](#Credits)
- [Get in touch](#Get-in-touch)


<h2 id="#introduction">Introduction</h2>
`Datamatrix-ml Pharmaceuticals` is one of the leading Pharmaceutical Manufacturing companies with a global presence. Their Markets are divided into different regions across the world. One of those regions manages the German and Poland Markets. But the company does not sell directly to customers. Instead, they work with a couple of Distributors in all their regions. They have an agreement with each distributor to share their Sales Data with them. This is to enable them to gain insights up to the retail level. 

<h2 id="#objective">Objective</h2>
Our aim is to perform in-depth data analysis to get insight into company sales performance. Specifically, we seek to answer the below questions…
* The company as a whole…
  * How is the company’s overall sales performance is By year and by month
  * Which are the top sales country,  top sales city, top-selling product class, and product
  * How is the company’s overall sales performance by year and sales channel/sub-channel=
* How distributors are contributing to business and who are our top customers. 
* How each of the sales team is performing? Who is the top sales rep? and which product class and product are each team selling most?

<h2 id="#dataset">Dataset</h2>
The dataset contains Pharmaceutical Manufacturing Company’s Wholesale-Retail Data. The field description of the raw data is given below. The raw dataset `pharma-data.csv` can be downloaded from [here](https://drive.google.com/file/d/1npKF_C2tG5psY-at4wvpEgh6T-7KHxEZ/view?usp=share_link)

|Field|Description|
|:---|:--|
|Distributor| Name of Wholesaler|
|Customer Name| Name of customer|
|City| Customer's city|
|Country| Customer's country|
|Latitude| Customer's Geo Latitude|
|Longitude| Customer's Geo Longitude|
|Channel|Class of buyer (Hospital, Pharmacy)|
|Sub-channel|Sector of the buyer (Government, Private, etc.)|
|Product Name|Name of Drug|
|Product Class|Class of Drug (Antibiotics, etc.)|
|Quantity|Quantity purchased|
|Price|Price product was sold for|
|Sales|Amount made from sale|
|Month|Month sale was made|
|Year|Year sale was made|
|Name of Sales Rep|Name of the Sales rep who facilitated the sale|
|Manager|Sales rep's Manager Name|
|Sales Team|Sale rep's team|

<h2 id="#solution-approach">Solution Approach</h2>
### Exploratory Data Analysis (EDA) [pandas]
To understand, be familiar with and check the sanity of the given data, the first step is EDA. In this project, the initial data exploration has been carried out using `pandas` python package. Here, in general, we are checking... 
 * Presence of any missing values 
 * Any unusual value (outliers) 
 * Incorrect values (e.g., sales column, we see -ve numbers)
 * Determine `categorical` and `numeric` columns
 * Determine dimensions of categorical columns and range of numeric columns
Note that these steps can be performed using `PowerQuery Editor` and/or excel; however, `pandas` makes it much easier and faster; on top of that, `pandas` can handle very large datasets.

EDA steps can be found in the `data-exploration.ipynb` notebook.

### Data Cleaning and Transform [PowerQuery Editor]
The provided dataset was relatively clean and well organized; hence not much work was required in this step; the following steps were carried out...
* Correct column heading provided
* Correct data type is assigned to columns

### Data Model Creation [PowerQuery Editor]
The provided data is in a single table format. The exploration revealed that it contains both categorical (`dimensions) and numeric (`facts`) data. Building a data model where dimensions and facts are separated is common in data analysis. Then they are linked together by logical relationship to form a `star schema.` The resultant data model is shown below...

<img src="https://github.com/sssingh/pharmaceutical-sales-analysis-powerbi/blob/main/images/data-model.png?raw=true"/>

the tables with the prefix `DIM` are dimension tables, and `FACT` is the fact table.

### Report Creation [PowerBI Desktop]
The report has been split into two levels
1. **Summary level report** (*Executive Summary Report*): This is a high-level report that shows the overall sales figures and elements at a glance.

[TODO: commentary]

<img src="https://github.com/sssingh/pharmaceutical-sales-analysis-powerbi/blob/main/images/exec-summary-page.png?raw=true"/>

2. **Detail level reports**:  
2a. *Distributor & Customer Analysis Report*: This is a more granular detailed report that analyses data from the company distributors' and customers' perspectives.
 
 [TODO: commentary]
 
 <img src="https://github.com/sssingh/pharmaceutical-sales-analysis-powerbi/blob/main/images/dist-cust-analysis-page.png?raw=true"/>
 
 &nbsp;&nbsp;&nbsp;2b. *Sales  Team Performance Report*: This is another detailed report that analyses the performance of the company's sales team.
 
 [TODO: commentary]
 
 <img src="https://github.com/sssingh/pharmaceutical-sales-analysis-powerbi/blob/main/images/sales-team-perform-page.png?raw=true"/>

<h2 id="#Conclusions">Conclusions</h2>

[TODO: Conclusions]

<h2 id="#How-To-Use">How To Use</h2>
### Read-only access via the web (Recommended)
[Open and view the report](https://app.powerbi.com/view?r=eyJrIjoiN2RkNGNjOTMtYmMxOC00NzY3LTg0OGEtMmY4YThlNWM5ZmMyIiwidCI6ImFlZDI3MWNkLTYzOTgtNDllZi1hOWNmLTQ4NDIyMTAxZTE0ZSIsImMiOjEwfQ%3D%3D&pageName=ReportSection) . It's a fully functional interactive report; feel free to experiment with it. 

### Full access via PowerBI desktop
If you have PowerBI desktop installed, download the `pharma-analysis.pbix` from the repo and open it using PowerBI desktop. There is no need to download the raw dataset; the `pbix` files contain the complete normalized data model.   

<h2 id="#License">License</h2>
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)

<h2 id="#Get-in-touch">Get in touch</h2>
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/sssingh)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/_sssingh)
[![website](https://img.shields.io/badge/website-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://datamatrix-ml.com/)

<h2 id="#Credits">Credits</h2>
- Dataset sourced from [Foresight BI](https://foresightbi.com.ng/practice-data/3-datasets-for-your-portfolio/)

[Back To The Top](#pharmaceutical-sales-analysis)
