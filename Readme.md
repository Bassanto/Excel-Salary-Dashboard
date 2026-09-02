# Excel Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This data jobs salary dashboard was built to help job seekers research salaries for their target roles and confirm they are being adequately compensated.

The data comes from my Excel course, which provided a foundation in analyzing data using this powerful tool. It contains detailed information on job titles, salaries, locations, and the essential skills tied to each role.

### Dashboard File
My final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were used for this analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023, sourced from my Excel course. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="/0_Resources/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** Used the bar chart feature, with formatted salary values and a layout optimized for clarity.
- 🎨 **Design Choice:** A horizontal bar chart for easy visual comparison of median salaries.
- 📉 **Data Organization:** Job titles sorted by descending salary for improved readability.
- 💡 **Insights Gained:** This makes salary trends easy to spot at a glance . Senior roles and Engineers pay more than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](/0_Resources/Images/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Used Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** A color-coded map to visually distinguish salary levels across regions.
- 📊 **Data Representation:** Median salary plotted for each country with available data.
- 👁️ **Visual Enhancement:** Improves readability and gives an immediate read on geographic salary trends.
- 💡 **Insights Gained:** Makes global salary disparities easy to grasp and highlights high- and low-paying regions.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles
#### 💰 Median Salary by Job Titles
~~~
=MEDIAN(
IF(
(jobs[job_title_short]=A2)*
(jobs[job_country]=country)*
(ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
(jobs[salary_year_avg]<>0),
jobs[salary_year_avg]
)
)
~~~

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, and schedule type, while excluding blank salaries.
- 📊 **Array Formula:** Uses the `MEDIAN()` function with a nested `IF()` statement to evaluate an array.
- 🎯 **Tailored Insights:** Returns salary information specific to job title, region, and schedule type.
- **🔢 Formula Purpose:** Populates the table below with the median salary for the specified job title, country, and type.

🍽️ Background Table

![1_Salary_Dashboard_Screenshot1.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="/0_Resources/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type
~~~
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
~~~
- 🔍 **Unique List Generation:** This formula uses the `FILTER()` function to exclude entries containing "and" or commas, and to omit zero values.
- **🔢 Formula Purpose:** Populates the table below with a list of unique job schedule types.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="/0_Resources/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Applying the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` fields in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 The dashboard's overall usability is improved

<img src="/0_Resources/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

I built this dashboard to surface insights into salary trends across various data-related job titles. Using data from my Excel course, it allows users to make informed decisions about their career paths , exploring how location and job type influence salaries along the way.