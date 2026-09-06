# HR Dashboard (Tableau)

An interactive Human Resources dashboard built in Tableau, covering headcount, hiring, attrition, department and location breakdowns, and workforce demographics — all with plain-language tooltips so non-technical stakeholders can read every chart at a glance.

![HR Dashboard preview](Summary_Dash.png)

## What's in this repo

| File | Description |
|---|---|
| `Hr_Dashboard.twbx` | The full Tableau packaged workbook (data + dashboard). Open with [Tableau Desktop](https://www.tableau.com/products/desktop) or [Tableau Public](https://public.tableau.com/). |
| `HumanResources.csv` | The underlying employee dataset that powers the dashboard. |
| `Summary_Dash.png` | A screenshot of the finished dashboard. |
| `HR_Dashboard_Chart_Tooltip_Report.docx` | A written report documenting every chart on the dashboard, what it shows, and how tooltips were designed for non-technical viewers. |

## Dashboard overview

The dashboard is organized into four sections:

- **Overview** — Active employee count, total hired vs. total terminated, hiring/termination trend over time, plus headcount by department and by location.
- **Demographics** — Gender split, and an age-vs-education breakdown.
- **Education & Performance** — A cross-tab of education level against performance rating.
- **Income** — Average salary by education level and gender, and average salary vs. age by job title.

### Key figures
- **7,984** active employees
- **8,950** total employees hired (all-time)
- **966** total employees terminated

### Where attrition lives
There's no single chart labeled "Attrition" — it's tracked through termination data instead:
- The **Terminated** big number (966) is the headline attrition figure.
- The **year-over-year trend line** next to it (in magenta/purple) shows whether attrition is rising or falling over time, plotted right alongside the Hired trend for comparison.
- The **Departments** and **Location** bar charts also break out terminated counts per category, so attrition can be compared across departments or offices.

## Dataset

`HumanResources.csv` contains one row per employee (8,950 rows), with the following fields:

`Employee_ID`, `First Name`, `Last Name`, `Gender`, `State`, `City`, `Education Level`, `Birthdate`, `Hiredate`, `Termdate`, `Department`, `Job Title`, `Salary`, `Performance Rating`

An employee is considered **active** if `Termdate` is blank, and **terminated** if it's populated.

## Tooltip design

Every chart uses a customized tooltip instead of Tableau's default, so a hover reads as a complete plain-language sentence (e.g. *"The total number of terminated employees is 966"*) with the key number bolded and highlighted, rather than raw field names. See `HR_Dashboard_Chart_Tooltip_Report.docx` for a full write-up, including a chart-by-chart inventory and tooltip examples.

## Tools used

- **Tableau** for the dashboard and visualizations
- **CSV** as the flat-file data source

## Getting started

1. Download `Hr_Dashboard.twbx`.
2. Open it in Tableau Desktop or upload it to Tableau Public.
3. The packaged workbook already includes the data extract, so no extra setup is needed.
