# 💼 Excel Salary Dashboard for Job Seekers

![Dashboard Overview](https://github.com/user-attachments/assets/bcc6aa30-fd7e-4bd5-9d4d-afe51b222235)

## 📘 Introduction

This Excel-based **Job Seekers Salary Dashboard** was created to help individuals explore data job salaries and assess if they are being adequately compensated.

The dashboard is built using a real-world 2023 dataset containing detailed information on job titles, salaries, locations, and required skills. This project demonstrates my ability to analyze, clean, and visualize data using core Excel features.

---

## 📂 Dashboard File

📎 [Download Dashboard File (1_Salary_Dashboard.xlsx)](1_Salary_Dashboard.xlsx)

---

## 🛠 Excel Skills Demonstrated

- 📊 **Charts** – Bar & Map visualizations  
- 🔢 **Formulas & Functions** – Dynamic calculations with multiple conditions  
- ✅ **Data Validation** – Dropdown filters and user-controlled selections

---

## 📚 Dataset Overview

The dataset used includes job data in the data science and tech industry from 2023:

- 🧑‍💼 **Job Titles**  
- 🌍 **Countries / Locations**  
- 💰 **Annual Salaries (USD)**  
- 🧠 **Skills & Job Types**

---

## 📈 Dashboard Visualizations

### 1. Job Titles vs Median Salaries

![Bar Chart – Job Titles](https://github.com/user-attachments/assets/833b8f8c-7391-4210-a66a-7be170ac81a4)

- **Excel Feature:** Horizontal bar chart with formatted currency values  
- **Insights:** Senior and engineering roles offer significantly higher compensation compared to entry-level analyst positions.

---

### 2. Country-wise Median Salaries (Map Chart)

![Map Chart – Countries](https://github.com/user-attachments/assets/513a2042-de55-4ebb-a682-965a36d25eef)

- **Excel Feature:** Map chart for visualizing salary differences across countries  
- **Insights:** Users can quickly identify high-paying job markets geographically.

---

## 📊 Key Excel Formulas

### 🔹 Median Salary by Job Title, Country, and Type

```excel
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
