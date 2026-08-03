# my_first_project_py

A beginner-friendly Python and SQL project that demonstrates core data analysis skills: creating a database, writing queries, and exporting results to CSV.

## 📌 What This Project Does

This project simulates a simple employee and department database. It demonstrates:

- Creating a SQLite database and tables
- Inserting sample data
- Writing and executing SQL queries
- Exporting query results to CSV files

## 📊 The Queries

This project includes **fourteen SQL queries** that build on each other:

| Query | Type | What It Does |
| :--- | :--- | :--- |
| **1** | `WHERE` | Filters employees by department |
| **2** | `JOIN` | Combines employee and department data |
| **3** | `WHERE >` | Finds employees earning above a threshold |
| **4** | `GROUP BY` + `SUM` | Total salary per department |
| **5** | `AVG`, `COUNT`, `ORDER BY` | Department stats |
| **6** | `HAVING` | Departments with avg salary > 70,000 |
| **7** | `ORDER BY DESC` | Departments ranked by total salary |
| **8** | Subquery | Employees above departmental average |
| **9** | CTE | Dept averages vs overall average |
| **10** | `ROW_NUMBER()` | Rank employees within department |
| **11** | `LEAD()` / `LAG()` | Compare to next/previous salary |
| **12** | `RANK()` / `DENSE_RANK()` | Compare ranking methods |
| **13** | `CASE WHEN` | High/low earner percentages |
| **14** | Outlier Detection | Employees above 120% of dept average |

## 📁 Files Generated

| File | Description |
| :--- | :--- |
| `engineering_team.csv` | Employees in Engineering |
| `employees_with_budgets.csv` | Employees with department budgets |
| `high_earners.csv` | Employees earning > 70,000 |
| `department_salary_totals.csv` | Total salary per department |
| `department_stats.csv` | Department stats |
| `high_avg_departments.csv` | Departments with avg salary > 70,000 |
| `ranked_departments.csv` | Departments ranked by total salary |
| `above_dept_avg.csv` | Employees above departmental average |
| `dept_vs_overall_avg.csv` | Dept averages vs overall average |
| `ranked_employees.csv` | Employees ranked within department |
| `salary_comparison.csv` | LEAD/LAG salary comparison |
| `rank_comparison.csv` | RANK vs DENSE_RANK |
| `conditional_aggregation.csv` | High/low earner percentages |
| `salary_outliers.csv` | Salary outliers |

## 🚀 How to Run It

```bash
git clone https://github.com/moyanebarney-rgb/my_first_project_py.git
cd my_first_project_py
python my_first_project.py| **Query 4** | Aggregation (`GROUP BY` + `SUM`) | Calculates total salary per department |
| **Query 5** | Aggregation + Sorting (`AVG`, `COUNT`, `ORDER BY`) | Department stats: employee count, average salary, total salary |
| **Query 6** | Filtered Aggregation (`HAVING`) | Departments where average salary exceeds 70,000 |
| **Query 7** | Ranking (`ORDER BY DESC`) | Departments ranked by total salary (highest first) |
| **Query 8** | Subquery | Employees earning above their department's average salary |
| **Query 9** | Common Table Expression (`WITH` / CTE) | Department averages compared to overall company average |
| **Query 10** | Window Function (`ROW_NUMBER()`) | Employees ranked by salary within their department |

---

## 📁 Files Generated

When you run the script, it generates the following CSV files:

| File | Description |
| :--- | :--- |
| `engineering_team.csv` | Employees in the Engineering department |
| `employees_with_budgets.csv` | Employees with their department budgets |
| `high_earners.csv` | Employees earning more than 70,000 |
| `department_salary_totals.csv` | Total salary per department |
| `department_stats.csv` | Department statistics (count, average salary, total salary) |
| `high_avg_departments.csv` | Departments where average salary > 70,000 |
| `ranked_departments.csv` | Departments ranked by total salary (highest first) |
| `above_dept_avg.csv` | Employees earning above their department's average salary |
| `dept_vs_overall_avg.csv` | Department averages compared to the overall company average |
| `ranked_employees.csv` | Employees ranked by salary within their department |

---

## 🚀 How to Run It

1. Clone this repository:
   ```bash
   git clone https://github.com/moyanebarney-rgb/my_first_project_py.git
```

2. Run the script in a Python environment:
   ```bash
   python my_first_project.py
   ```
3. The script will generate ten CSV files with the query results.

---

🧠 Why This Matters

These are the same skills used in fiscal data analysis:

· Filtering to isolate specific departments or spending categories
· Joining to combine datasets (e.g., linking SOE financials to budget allocations)
· Aggregating to calculate totals (e.g., total maintenance spend per SOE)
· Sorting to identify highest-cost areas
· Filtering aggregates to find departments or categories that exceed thresholds
· Ranking to compare performance or spending across categories
· Subqueries to compare individual performance against averages
· Common Table Expressions (CTEs) to structure complex fiscal reports
· Window Functions to rank or compare items within groups

This project is a foundation for more advanced data work in public finance and infrastructure economics.

---

📂 Repository Structure

```
my_first_project_py/
├── my_first_project.py          # Main Python script
├── README.md                    # This file
├── engineering_team.csv         # Output from Query 1
├── employees_with_budgets.csv   # Output from Query 2
├── high_earners.csv             # Output from Query 3
├── department_salary_totals.csv # Output from Query 4
├── department_stats.csv         # Output from Query 5
├── high_avg_departments.csv     # Output from Query 6
├── ranked_departments.csv       # Output from Query 7
├── above_dept_avg.csv           # Output from Query 8
├── dept_vs_overall_avg.csv      # Output from Query 9
├── ranked_employees.csv         # Output from Query 10
└── my_data.db                   # SQLite database (generated)
```

---

📧 Author

Samkele Barney Moyane
Aspiring Fiscal Technocrat | Infrastructure Economics | Data Analysis

---

📝 License

This project is for educational and portfolio purposes.

```

---

## ✅ WHAT TO DO NOW

| Step | Action |
| :--- | :--- |
| **1** | Go to your repository: `https://github.com/moyanebarney-rgb/my_first_project_py` |
| **2** | Open `README.md` (click it, then click the pencil icon to edit) |
| **3** | **Select everything** (Ctrl+A / Cmd+A) |
| **4** | **Delete everything** |
| **5** | **Paste the clean README above** |
| **6** | Scroll down, write commit message: `Clean README — 10 queries complete` |
| **7** | Click **Commit changes** |
