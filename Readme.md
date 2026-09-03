# Excel Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)
<img width="1096" height="504" alt="Excel_dashboard" src="https://github.com/user-attachments/assets/c6c56a56-54d5-441b-b210-2617d162bfb5" />


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



<img width="437" height="242" alt="Screenshot 2026-09-02 233637" src="https://github.com/user-attachments/assets/4d1033ff-a344-4d0f-8179-bea05d7d1b20" />

- 🛠️ **Excel Features:** Used the bar chart feature, with formatted salary values and a layout optimized for clarity.
- 🎨 **Design Choice:** A horizontal bar chart for easy visual comparison of median salaries.
- 📉 **Data Organization:** Job titles sorted by descending salary for improved readability.
- 💡 **Insights Gained:** This makes salary trends easy to spot at a glance . Senior roles and Engineers pay more than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

<img width="353" height="251" alt="Screenshot 2026-09-02 234213" src="https://github.com/user-attachments/assets/e2e38039-4915-4c56-8a06-050f6f9fb148" />







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

<img width="275" height="219" alt="Screenshot 2026-09-03 154033" src="https://github.com/user-attachments/assets/ca318e1e-dfd0-405d-b01c-876231266cdc" />


📉 Dashboard Implementation

https://github.com/user-attachments/assets/79a37d3f-220e-46b5-a4b3-4aabe48c3cf3



#### ⏰ Count of Job Schedule Type
~~~
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
~~~
- 🔍 **Unique List Generation:** This formula uses the `FILTER()` function to exclude entries containing "and" or commas, and to omit zero values.
- **🔢 Formula Purpose:** Populates the table below with a list of unique job schedule types.

🍽️ Background Table

<img width="233" height="120" alt="Type_schedule_table" src="https://github.com/user-attachments/assets/5127ab3d-2dc1-49c5-ac1a-7a4f6af4fc72" />


### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Applying the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` fields in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 The dashboard's overall usability is improved


## Conclusion

I built this dashboard to surface insights into salary trends across various data-related job titles. Using data from my Excel course, it allows users to make informed decisions about their career paths , exploring how location and job type influence salaries along the way.
