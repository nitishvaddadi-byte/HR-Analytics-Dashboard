# HR Analytics Dashboard | Power BI

An interactive HR Analytics Dashboard built using Power BI to analyze employee demographics, recruitment, performance, and training data. The dashboard provides insights through KPI cards, charts, slicers, and interactive page navigation.

---

## 📌 Project Overview

The HR Analytics Dashboard is a data visualization project developed using Microsoft Power BI. It focuses on analyzing employee-related data to understand workforce distribution, performance, recruitment patterns, and training outcomes.

The dashboard consists of four interactive pages: Overview, Employee Analysis, Performance, and Training Analysis. Each page provides a different perspective on the dataset, allowing users to explore employee information and identify patterns through interactive visualizations.

The project demonstrates the use of Power Query for data cleaning, DAX for calculations, and Power BI for building interactive dashboards.

---

## 🎯 Project Objectives

- Analyze employee distribution across departments and regions.
- Understand employee demographics based on age, gender, and education.
- Examine employee recruitment channels.
- Analyze employee performance using KPI achievements, previous-year ratings, and awards.
- Evaluate employee training participation and average training scores.
- Develop an interactive dashboard for exploring HR data.
- Present workforce insights through clear and informative visualizations.

---

## 🛠️ Tools and Technologies

| Tool | Purpose |
|---|---|
| Microsoft Power BI | Dashboard development and data visualization |
| Power Query | Data cleaning and transformation |
| DAX | Calculated measures and calculated columns |
| CSV | Dataset storage and data source |
| GitHub | Project version control and documentation |

---

## 📂 Dataset Information

**Dataset Name:** Employee's Performance for HR Analytics

**File:** `HR.csv`

The dataset contains employee information related to demographics, recruitment, performance, and training.

### Dataset Columns

| Column Name | Description |
|---|---|
| employee_id | Unique identifier assigned to an employee |
| department | Department to which the employee belongs |
| region | Region associated with the employee |
| education | Employee's education level |
| gender | Employee's gender |
| recruitment_channel | Channel through which the employee was recruited |
| no_of_trainings | Number of training sessions |
| age | Employee's age |
| previous_year_rating | Employee's performance rating from the previous year |
| length_of_service | Number of years of service |
| KPIs_met_more_than_80 | Indicates whether the employee met more than 80% of KPIs |
| awards_won | Indicates whether the employee received an award |
| avg_training_score | Employee's average training score |

### Dataset Summary

- **Original Records:** 17,417
- **Columns:** 13
- **Data Format:** CSV
- **Data Domain:** Human Resources Analytics

The dataset contains missing values in the `education` and `previous_year_rating` columns. Missing previous-year ratings were preserved rather than replaced with assumed values.

---

## 🧹 Data Cleaning and Transformation

Data cleaning and transformation were performed using Power Query in Power BI.

The following operations were carried out:

- Inspected the dataset and reviewed column names and data types.
- Checked for missing values and duplicate records.
- Removed exact duplicate rows.
- Reviewed records with repeated employee IDs.
- Checked for data errors.
- Standardized gender values from `m` and `f` to `Male` and `Female`.
- Created age groups for demographic analysis.
- Preserved missing previous-year ratings instead of assigning arbitrary values.

### Age Group Categorization

A calculated column was created to group employees into age categories.

| Age Group | Age Range |
|---|---|
| Below 25 | Less than 25 |
| 25–34 | 25 to 34 |
| 35–44 | 35 to 44 |
| 45–54 | 45 to 54 |
| 55 and Above | 55 and above |

These categories were used to analyze employee demographics.

---

## 📊 Dashboard Pages

The dashboard consists of four pages, each designed to analyze a specific aspect of HR data.

### 1. Overview

The Overview page provides a summary of employee demographics and key workforce metrics.

**KPI Cards:**
- Total Employees
- Average Age
- Average Training Score
- Employees Meeting KPIs

**Visualizations:**
- Employee Distribution by Department
- Employee Distribution by Gender
- Employee Distribution by Age Group
- Employee Distribution by Education

**Interactive Filters:**
- Department
- Gender

This page provides a high-level overview of the workforce and allows users to filter employee data interactively.

### 2. Employee Analysis

The Employee Analysis page focuses on workforce distribution, recruitment channels, and employee service information.

**Visualizations:**
- Employee Distribution by Recruitment Channel
- Employee Distribution by Region
- Average Training Score by Department
- Average Length of Service by Department

This page allows users to explore recruitment patterns, regional workforce distribution, and differences in training scores and service length across departments.

### 3. Performance

The Performance page focuses on employee KPI achievement, previous-year ratings, and awards.

**Visualizations:**
- Employees Meeting KPIs by Department
- Employee Distribution by Previous Year Rating
- Awards Won by Department
- KPI Achievement by Previous Year Rating

This page helps users examine employee performance patterns and compare KPI achievements across departments and previous-year rating categories.

### 4. Training Analysis

The Training Analysis page focuses on training participation and employee training scores.

**Visualizations:**
- Employee Distribution by Number of Trainings
- Average Training Score by Number of Trainings
- Average Training Score by Department
- Average Number of Trainings by Department

This page allows users to explore training participation and compare average training scores across training counts and departments.

---

## 📐 DAX Measures

DAX was used to create measures for the KPI cards and visualizations.

### 1. Total Employees

Calculates the number of distinct employee IDs.

```dax
Total Employees =
DISTINCTCOUNT(HR[employee_id])
```

### 2. Average Age

Calculates the average age of employees.

```dax
Average Age =
AVERAGE(HR[age])
```

### 3. Average Training Score

Calculates the average training score.

```dax
Average Training Score =
AVERAGE(HR[avg_training_score])
```

### 4. Employees Meeting KPIs

Calculates the number of distinct employee IDs with a KPI achievement value of 1.

```dax
Employees Meeting KPIs =
CALCULATE(
    DISTINCTCOUNT(HR[employee_id]),
    HR[KPIs_met_more_than_80] = 1
)
```

**Note:** The dataset contains repeated employee IDs. Therefore, distinct-count measures count unique IDs rather than individual records. These measures should not automatically be interpreted as verified employee headcounts.

---

## ⭐ Key Features

- Interactive KPI cards for summarizing HR metrics.
- Interactive department and gender slicers.
- Four dashboard pages covering different HR analysis areas.
- Interactive page navigation between dashboard pages.
- Employee demographic analysis.
- Recruitment channel and regional distribution analysis.
- Employee performance and KPI achievement analysis.
- Training participation and training score analysis.
- Data cleaning and transformation using Power Query.
- DAX measures for calculating key metrics.
- Visual representation of HR data for easier exploration.

---

## 📈 Key Areas of Analysis

The dashboard supports analysis of the following areas:

**Employee Demographics**
- Distribution of employees by age group.
- Gender distribution.
- Education-level distribution.
- Department-wise employee distribution.

**Recruitment Analysis**
- Employee distribution by recruitment channel.
- Employee distribution across regions.

**Performance Analysis**
- KPI achievement across departments.
- Distribution of previous-year performance ratings.
- Awards across departments.
- KPI achievement by previous-year rating.

**Training Analysis**
- Number of training sessions attended.
- Average training scores by training count.
- Department-wise average training scores.
- Department-wise average number of training sessions.

---

## 📷 Dashboard Screenshots

Screenshots of the four dashboard pages can be added below.

### Overview
![Overview Dashboard](screenshots/overview.png)

### Employee Analysis
![Employee Analysis Dashboard](screenshots/employee-analysis.png)

### Performance
![Performance Dashboard](screenshots/performance.png)

### Training Analysis
![Training Analysis Dashboard](screenshots/training-analysis.png)

---

## 📁 Project Structure

```text
HR-Analytics-Dashboard/
│
├── HR_Analytics_Dashboard.pbix
│
├── HR.csv
│
├── README.md
│
└── screenshots/
    ├── overview.png
    ├── employee-analysis.png
    ├── performance.png
    └── training-analysis.png
```

---

## 🚀 How to Run the Project

Follow these steps to explore the dashboard.

1. Clone or download this repository.
2. Install Microsoft Power BI Desktop.
3. Open `HR_Analytics_Dashboard.pbix` in Power BI Desktop.
4. If Power BI asks for the dataset location, select the `HR.csv` file.
5. Refresh the data if required.
6. Explore the four dashboard pages using the sidebar navigation.
7. Use the available slicers to filter the data.

---

## 🔍 Insights and Exploration

The dashboard provides an interactive way to explore employee demographics, recruitment patterns, performance, and training.

Users can investigate questions such as:

- How are employees distributed across departments?
- What is the distribution of employees across different age groups?
- Which recruitment channels are represented in the dataset?
- How do average training scores vary across departments?
- How many employees met more than 80% of their KPIs?
- How are KPI achievements distributed across previous-year ratings?
- How does the average training score vary with the number of training sessions?

The dashboard is designed to support these investigations rather than assume conclusions from the visualizations.

---

## 📚 Skills Demonstrated

- Data Cleaning
- Data Transformation
- Exploratory Data Analysis
- Data Visualization
- Power Query
- DAX
- KPI Development
- Interactive Dashboard Design
- Business Intelligence
- HR Analytics

---

## 👨‍💻 Author

**v.sai nitish**

B.Tech in Computer Science and Engineering  
Specialization: Data Science

**Technical Skills:**  
Power BI | SQL | Python | Excel | Data Analysis

---

## 📌 Project Status

**Status:** Completed

**Project Type:** Data Analytics / Business Intelligence

**Domain:** Human Resources Analytics

**Tool:** Microsoft Power BI

---
