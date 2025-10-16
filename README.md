# HR Analytics Dashboard – Power BI

Analyze sample HR data with an interactive, fully-featured Power BI dashboard.

## Project Overview

This project demonstrates end-to-end HR data analysis using Power BI, including:
- Data import and cleaning with Power Query
- KPI & metric calculations (Headcount, Salary, Leave, etc.)
- Custom DAX formulas for advanced analytics
- Interactive dashboard design and visuals
- Dynamic filters and slicers for deeper insights

**Live dashboard:**  
[Power BI Report](https://app.powerbi.com/groups/me/reports/8adf30c0-3ac3-4c17-9636-afe8d79ea4c6/d37e63d35ecfaf31fcc6?experience=power-bi)

## Features & Analysis

- Job title headcounts and distributions
- Gender breakdown (overall and per job)
- Age spread of staff (with histogram binning)
- Salary analysis by job title (average, min, max)
- Top earners per job role
- Scatter plot: Qualification vs. Salary
- Staff growth trends (cumulative headcount over time)
- Employee filtering by name initials
- Leave balance analytics (overall, breakdown > 20 days)
- All-in-one HR dashboard page with key KPIs

## Dashboard Snapshots

![HR Dashboard Screenshot](dashboard.jpg)

## Dataset

**Source:** Sample HR Dataset (Excel format)

Typical fields:
- Name
- Employee ID
- Gender
- Educational Qualification
- Date of Join
- Job Title
- Salary
- Age
- Leave Balance

## Key DAX Formulas

- **Headcount**
  
Headcount = COUNTROWS(staff)

- **Average Salary**
  
AvgSalary = AVERAGE(staff[Salary])

- **Cumulative Headcount**
  
CumulativeHeadcount = CALCULATE(
[Headcount],
FILTER(ALL(staff[Date of Join]), staff[Date of Join] <= MAX(staff[Date of Join]))
)

- **Leave Balance Over 20 Days**
  
LBLover20days = CALCULATE([Headcount], staff[Leave Balance] > 20)

- **Minimum and Maximum Salary by Job Title**
  
MinSalary = MIN(staff[Salary])
MaxSalary = MAX(staff[Salary])

## Usage

- Clone or download this repository
- Open the `.pbix` file with Power BI Desktop
- Load or connect the sample data
- Explore interactive visuals and DAX measures
- Modify or extend as required

## Credits

Dashboard, DAX, and workflow: Prajwal Nagaraj

