# Salary Dashboard

![1_Salary_Dashboard.png](1_Salary_Final_Dashboard.png)

## Introduction

This salary dashboard was created to help job seekers investigate salaries for their desired roles and ensure they are being adequately compensated.

The dashboard provides comprehensive insights into data science job market trends, featuring real-world salary data across different job titles, countries, and employment types. The interactive visualizations enable quick identification of salary patterns and geographic disparities in the data science field.

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset contains real-world data science job information from 2023-2024, aggregated from major job platforms. It includes detailed information on:

- **👨‍💼 Job titles** (10+ data science roles)
- **💰 Salaries** (ranging from $0K to $160K+)
- **📍 Locations** (United States and international markets)
- **🛠️ Employment types** (Full-time, Part-time, Contract, Temporary, Internship)

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

![1_Salary_Dashboard_Screenshot1.png](1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

<img src="1_Salary_Dashboard_Type.png" width="425" height="400" alt="Salary Dashboard Data Validation">

### 🤔 So What

This analysis shows that roles requiring deeper technical skills such as Python and SQL tend to offer higher median compensation. Employers appear to prioritize candidates with strong programming and data manipulation abilities, indicating that technical proficiency can be a key differentiator in competitive job markets.


## 🔎 Key Business Insights

- Senior-level roles consistently command higher median salaries.
- U.S.-based roles show stronger compensation compared to international markets.
- Employment type significantly influences salary levels.
- Engineers tend to earn more than Analyst-focused roles.

## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from https://datanerd.tech/, this dashboard allows users to make informed decisions about their career paths. The dashboard enables users to explore how location and job type influence salary outcomes.

