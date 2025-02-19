# Excel Salary Dashboard

![Screenshot 2025-02-10 154848](https://github.com/user-attachments/assets/bcc6aa30-fd7e-4bd5-9d4d-afe51b222235)


## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. 

The data which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File
My final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas and Functions**
- **Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via excel which provides a foundation for analyzing data using Excel. It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Dashboard Build

### 📉 Charts

#### Data Science Job Salaries - Bar Chart

![1_Salary_Dashboard_Job_Title](https://github.com/user-attachments/assets/833b8f8c-7391-4210-a66a-7be170ac81a4)


- **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
  **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- **Data Organization:** Sorted job titles by descending salary for improved readability.
- **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

####  Country Median Salaries - Map Chart


![1_Salary_Dashboard_Country_Map](https://github.com/user-attachments/assets/513a2042-de55-4ebb-a682-965a36d25eef)



### Formulas and Functions

####  Median Salary by Job Titles

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

-  **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
-  **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
-  **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- ** Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.
 Dashboard Implementation

![1_Salary_Dashboard_Data_Validation](https://github.com/user-attachments/assets/1a45d3c5-abb4-498f-bfb3-46e554884166)


####  Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- ** Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.



####  Filtered List

-  **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    -  User input is restricted to predefined, validated schedule types
    -  Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is enhanced

<img src="/0_Resources/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from  Excel , this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
